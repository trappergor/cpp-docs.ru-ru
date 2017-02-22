---
title: "Использование плиток | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Использование плиток
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Можно использовать заполнение плитками для максимального ускорения приложения.  Заполнение плитками делит поток на равные прямоугольные подмножества, или *плитки*.  При использовании соответствующего размера мозаики и мозаичного алгоритма можно достичь еще большего ускорения в коде C\+\+ AMP.  Основные компоненты мозаичного заполнения:  
  
-   Переменные `tile_static`.  Основное преимущество мозаичного замощения — выигрыш в производительности при доступе к `tile_static`.  Доступ к данным в памяти `tile_static` может быть значительно быстрее, чем доступ к данным в глобальной области \(объекты `array` или `array_view`\).  Экземпляр переменной `tile_static` создается для каждой мозаики, и все потоки в мозаике имеют доступ к этой переменной.  В типичном мозаичном алгоритме данные копируются в память `tile_static` сразу из глобальной памяти, а затем к ним многократно обращаются из памяти `tile_static`.  
  
-   [Метод tile\_barrier::wait](../Topic/tile_barrier::wait%20Method.md).  Вызов `tile_barrier::wait` приостанавливает выполнение текущего потока до тех пор, пока все потоки в одной и той же мозаике не достигнут вызова `tile_barrier::wait`.  Невозможно гарантировать порядок, в котором будут выполняться потоки, но можно гарантировать то, что ни один поток в плитке не будет выполняться после вызова `tile_barrier::wait` до тех пор, пока все потоки не достигнут этого вызова.  Это означает, что с помощью метода `tile_barrier::wait` можно выполнить задачи методом "плитка\-за\-плиткой", нежели чем методом "поток\-за\-потоком".  Типичный алгоритм мозаичного заполнения содержит код для инициализации памяти `tile_static` для всей мозаики, за которым следует вызов `tile_barrer::wait`.  Код, следующий за `tile_barrier::wait`, содержит вычисления, требующие доступа ко всем значениям `tile_static`.  
  
-   Локальная и глобальная индексация.  Имеется доступ к индексу потока по отношению к всему `array_view` или объекту `array` и к индексу относительно плитки.  Использование локального индекса может сделать код более удобным для чтения и отладки.  Обычно используется локальное индексирование для доступа к переменным `tile_static`, и глобальное индексирование для доступа к переменным `array` и `array_view`.  
  
-   [Класс tiled\_extent](../../parallel/amp/reference/tiled-extent-class.md) и [Класс tiled\_index](../../parallel/amp/reference/tiled-index-class.md).  Можно использовать объект `tiled_extent` вместо объекта `extent` в вызове `parallel_for_each`.  Можно использовать объект `tiled_index` вместо объекта `index` в вызове `parallel_for_each`.  
  
 Чтобы воспользоваться преимуществами мозаичного замощения, алгоритм должен разбить вычислительный домен на плитки, а затем скопировать данные плиток в переменные `tile_static` для ускорения доступа.  
  
## Пример глобального, мозаичного и локального индексов  
 Следующая схема представляет матрицу данных 8x9, которые распределяются по плиткам 2x3.  
  
 ![Матрица 8x9, разделенная на плитки 2x3](../../parallel/amp/media/usingtilesmatrix.png "UsingTilesMatrix")  
  
 Следующий пример демонстрирует глобальные, мозаичные и локальные индексы в данной мозаичной матрице.  Объект `array_view` создается с помощью элементов типа `Description`.  Элемент `Description` содержит глобальный, мозаичный и локальный индексы элемента в матрице.  Код в вызове метода `parallel_for_each` устанавливает значения глобального, мозаичного и локального индексов каждого элемента.  Вывод показывает значения в структурах `Description`.  
  
```cpp  
  
#include <iostream>  
#include <iomanip>  
#include <Windows.h>  
#include <amp.h>  
using namespace concurrency;  
  
const int ROWS = 8;  
const int COLS = 9;  
  
// tileRow and tileColumn specify the tile that each thread is in.  
// globalRow and globalColumn specify the location of the thread in the array_view.  
// localRow and localColumn specify the location of the thread relative to the tile.  
struct Description {  
    int value;  
    int tileRow;  
    int tileColumn;  
    int globalRow;  
    int globalColumn;  
    int localRow;  
    int localColumn;  
};  
  
// A helper function for formatting the output.  
void SetConsoleColor(int color) {  
    int colorValue = (color == 0) ? 4 : 2;  
    SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE), colorValue);  
}  
  
// A helper function for formatting the output.  
void SetConsoleSize(int height, int width) {  
    COORD coord; coord.X = width; coord.Y = height;  
    SetConsoleScreenBufferSize(GetStdHandle(STD_OUTPUT_HANDLE), coord);  
    SMALL_RECT* rect = new SMALL_RECT();  
    rect->Left = 0; rect->Top = 0; rect->Right = width; rect->Bottom = height;  
    SetConsoleWindowInfo(GetStdHandle(STD_OUTPUT_HANDLE), true, rect);  
}  
  
// This method creates an 8x9 matrix of Description structures. In the call to parallel_for_each, the structure is updated   
// with tile, global, and local indices.  
void TilingDescription() {  
    // Create 72 (8x9) Description structures.  
    std::vector<Description> descs;  
    for (int i = 0; i < ROWS * COLS; i++) {  
        Description d = {i, 0, 0, 0, 0, 0, 0};  
        descs.push_back(d);  
    }  
  
    // Create an array_view from the Description structures.  
    extent<2> matrix(ROWS, COLS);  
    array_view<Description, 2> descriptions(matrix, descs);  
  
    // Update each Description with the tile, global, and local indices.  
    parallel_for_each(descriptions.extent.tile< 2, 3>(),  
         [=] (tiled_index< 2, 3> t_idx) restrict(amp)   
    {  
        descriptions[t_idx].globalRow = t_idx.global[0];  
        descriptions[t_idx].globalColumn = t_idx.global[1];  
        descriptions[t_idx].tileRow = t_idx.tile[0];  
        descriptions[t_idx].tileColumn = t_idx.tile[1];  
        descriptions[t_idx].localRow = t_idx.local[0];  
        descriptions[t_idx].localColumn= t_idx.local[1];  
    });  
  
    // Print out the Description structure for each element in the matrix.  
    // Tiles are displayed in red and green to distinguish them from each other.  
    SetConsoleSize(100, 150);  
    for (int row = 0; row < ROWS; row++) {  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Value: " << std::setw(2) << descriptions(row, column).value << "      ";  
        }  
        std::cout << "\n";  
  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Tile:   " << "(" << descriptions(row, column).tileRow << "," << descriptions(row, column).tileColumn << ")  ";  
        }  
        std::cout << "\n";  
  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Global: " << "(" << descriptions(row, column).globalRow << "," << descriptions(row, column).globalColumn << ")  ";  
        }  
        std::cout << "\n";  
  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Local:  " << "(" << descriptions(row, column).localRow << "," << descriptions(row, column).localColumn << ")  ";  
        }  
        std::cout << "\n";  
        std::cout << "\n";  
    }  
}  
  
void main() {  
    TilingDescription();  
    char wait;  
    std::cin >> wait;  
}  
  
```  
  
 Основная задача примера в определении объекта `array_view` и вызове `parallel_for_each`.  
  
1.  Вектор структур `Description` копируется в объект 8x9 `array_view`.  
  
2.  Метод `parallel_for_each` вызывается с объектом `tiled_extent` как вычислительный домен.  Объект `tiled_extent` создается путем вызова метода `extent::tile()` переменной `descriptions`.  Параметры типа вызова `extent::tile()`, `<2,3>`, указывают, что создаются плитки 2x3.  Таким образом, матрица 8x9 разделена на 12 плиток, 4 строки и 3 столбца.  
  
3.  Метод `parallel_for_each` вызывается с помощью объекта `tiled_index<2,3>` \(`t_idx`\) в качестве индекса.  Параметры типа индекса \(`t_idx`\) должны соответствовать параметрам типов вычислительного домена\(`descriptions.extent.tile< 2, 3>()`\).  
  
4.  Когда каждый поток выполняется, индекс `t_idx` возвращает сведения о том, в какой плитке находится поток \(свойство `tiled_index::tile`\), и расположение потока внутри плитки \(свойство `tiled_index::local`\).  
  
## Синхронизация плитки — tile\_static и tile\_barrier::wait  
 Предыдущий пример иллюстрирует структуру и индексы мозаики, но в действительности он не очень полезен.  Заполнение плитками будет полезным, когда плитки встроены в алгоритм и используют переменные `tile_static`.  Поскольку все потоки в мозаике имеют доступ к переменным `tile_static`, вызовы `tile_barrier::wait` используются для синхронизации доступа к переменным `tile_static`.  Хотя все потоки в мозаике имеют доступ к переменным `tile_static`, не существует гарантированного порядка выполнения потоков в мозаике.  В следующем примере показано, как использовать переменные `tile_static` и метод `tile_barrier::wait`, чтобы вычислить среднее значение каждой плитки.  Ниже приведены основные положения для понимания примера:  
  
1.  Необработанные данные rawData хранятся в матрице 8x8.  
  
2.  Размер плитки — 2x2.  Это создает сетку размера 4x4 из плиток, а средние значения можно хранить в матрице 4x4 используя объект `array`.  Есть только ограниченное число типов, которые можно перенаправить по ссылке в AMP\-ограниченную функцию.  Класс `array` — один из них.  
  
3.  Размер матрицы и размер образца определяются с помощью выражений `#define`, поскольку параметры типа в `array`, `array_view`, `extent` и `tiled_index` должны быть константными значениями.  Можно также использовать объявления `const int static`.  В качестве дополнительного преимущества изменение размера образца тривиально для вычисления среднего значения в мозаиках 4х4.  
  
4.  Массив `tile_static` 2x2 значений типа float объявляется для каждой мозаики.  Хотя объявление находится в пути кода для каждого потока, только один массив создается для каждой мозаики в матрице.  
  
5.  Есть строка кода для копирования значений из каждой плитки в массив `tile_static`.  Для каждого потока после копирования значения в массив выполнение в потоке останавливается из\-за вызова `tile_barrier::wait`.  
  
6.  Когда все потоки в мозаике достигли барьера, можно вычислить среднее значение.  Поскольку код выполняется для каждого потока, есть оператор `if` для вычисления среднего значения только в одном потоке.  Среднее значение хранится в переменной averages.  Барьер, по существу, — конструкция, которая контролирует вычисления по плиткам, во многом аналогичная циклу `for`.  
  
7.  Данные в переменной `averages`, так как она — объект `array`, должны быть скопированы обратно на узел.  Этот пример использует оператор преобразования вектора.  
  
8.  В окончательном примере можно изменить значение SAMPLESIZE на 4, и код выполнится правильно без каких\-либо других изменений.  
  
```cpp  
  
#include <iostream>  
#include <amp.h>  
using namespace concurrency;  
  
#define SAMPLESIZE 2  
#define MATRIXSIZE 8  
void SamplingExample() {  
  
    // Create data and array_view for the matrix.  
    std::vector<float> rawData;  
    for (int i = 0; i < MATRIXSIZE * MATRIXSIZE; i++) {  
        rawData.push_back((float)i);  
    }  
    extent<2> dataExtent(MATRIXSIZE, MATRIXSIZE);  
    array_view<float, 2> matrix(dataExtent, rawData);  
  
    // Create the array for the averages.  
    // There is one element in the output for each tile in the data.  
    std::vector<float> outputData;  
    int outputSize = MATRIXSIZE / SAMPLESIZE;  
    for (int j = 0; j < outputSize * outputSize; j++) {  
        outputData.push_back((float)0);  
    }  
    extent<2> outputExtent(MATRIXSIZE / SAMPLESIZE, MATRIXSIZE / SAMPLESIZE);  
    array<float, 2> averages(outputExtent, outputData.begin(), outputData.end());  
  
    // Use tiles that are SAMPLESIZE x SAMPLESIZE.  
    // Find the average of the values in each tile.  
    // The only reference-type variable you can pass into the parallel_for_each call  
    // is a concurrency::array.  
    parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),  
         [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)   
    {  
        // Copy the values of the tile into a tile-sized array.  
        tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];  
        tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];  
  
        // Wait for the tile-sized array to load before you calculate the average.  
        t_idx.barrier.wait();  
  
        // If you remove the if statement, then the calculation executes for every  
        // thread in the tile, and makes the same assignment to averages each time.  
        if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {  
            for (int trow = 0; trow < SAMPLESIZE; trow++) {  
                for (int tcol = 0; tcol < SAMPLESIZE; tcol++) {  
                    averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];  
                }  
            }  
            averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);  
        }  
    });  
  
    // Print out the results.  
    // You cannot access the values in averages directly. You must copy them  
    // back to a CPU variable.  
    outputData = averages;  
    for (int row = 0; row < outputSize; row++) {  
        for (int col = 0; col < outputSize; col++) {  
            std::cout << outputData[row*outputSize + col] << " ";  
        }  
        std::cout << "\n";  
    }  
    // Output for SAMPLESSIZE = 2 is:  
    //  4.5  6.5  8.5 10.5  
    // 20.5 22.5 24.5 26.5  
    // 36.5 38.5 40.5 42.5  
    // 52.5 54.5 56.5 58.5  
  
    // Output for SAMPLESIZE = 4 is:  
    // 13.5 17.5  
    // 45.5 49.5  
}  
  
int main() {  
    SamplingExample();  
}  
  
```  
  
## Состояние гонки  
 Было бы интересно создать переменную `tile_static` с именем `total` и увеличивать эту переменную для каждого потока:  
  
```cpp  
  
// Do not do this.  
tile_static float total;  
total += matrix[t_idx];  
t_idx.barrier.wait();  
averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);  
  
```  
  
 Первая проблема в этом подходе, это что переменные `tile_static` не могут иметь инициализаторы.  Вторая проблема заключается в том, что существует состояние гонки при присваивании переменной `total`, поскольку все потоки в плитке имеют доступ к этой переменной без установленного порядка.  Можно запрограммировать алгоритм так, чтобы разрешить доступ к целому только одному потоку на каждом барьере, как показано далее.  Однако, это решение не расширяется.  
  
```cpp  
  
// Do not do this.  
tile_static float total;  
if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {  
    total = matrix[t_idx];  
}  
t_idx.barrier.wait();  
  
if (t_idx.local[0] == 0 && t_idx.local[1] == 1) {  
    total += matrix[t_idx];  
}  
t_idx.barrier.wait();  
  
// etc.  
  
```  
  
## Барьеры памяти  
 Существует два типа доступа к памяти, которые должны быть синхронизированы — доступ к глобальной памяти и доступ к памяти `tile_static`.  Объект `concurrency::array` выделяет только глобальную память.  Объект `concurrency::array_view` может ссылаться на глобальную память, память `tile_static` или на обе сразу в зависимости от того, как он был создан.  Существует два типа памяти, которая должна быть синхронизирована:  
  
-   глобальная память  
  
-   `tile_static`  
  
 *Барьер памяти* гарантирует, что доступ к памяти предоставляется другим потокам в мозаике потоков и осуществляется в соответствии с порядком выполнения операций в программе.  Чтобы это обеспечить, компиляторы и процессоры не переупорядочивают чтения и записи через барьер.  В C\+\+ AMP барьер памяти создается путем вызова одного из следующих методов.  
  
-   [Метод tile\_barrier::wait](../Topic/tile_barrier::wait%20Method.md): Создает барьер вокруг глобальной памяти и памяти `tile_static`.  
  
-   [Метод tile\_barrier::wait\_with\_all\_memory\_fence](../Topic/tile_barrier::wait_with_all_memory_fence%20Method.md): Создает барьер вокруг глобальной памяти и памяти `tile_static`.  
  
-   [Метод tile\_barrier::wait\_with\_global\_memory\_fence](../Topic/tile_barrier::wait_with_global_memory_fence%20Method.md): Создает барьер только вокруг глобальной памяти.  
  
-   [Метод tile\_barrier::wait\_with\_tile\_static\_memory\_fence](../Topic/tile_barrier::wait_with_tile_static_memory_fence%20Method.md): Создает барьер только вокруг памяти `tile_static`.  
  
 Вызов конкретного барьера, которой требуется, может повысить производительность приложения.  Тип барьера влияет на то, как компилятор и оборудование переупорядочивает выражения.  Например, при использовании барьера глобальной памяти он применяется только к операциям доступа к глобальной памяти и, следовательно, компилятор и оборудование могут изменять порядок чтения переменных `tile_static` и записи в них на обеих сторонах барьера.  
  
 В следующем примере барьер синхронизирует записи в переменную `tileValues` типа `tile_static`.  В этом примере `tile_barrier::wait_with_tile_static_memory_fence` вызывается вместо `tile_barrier::wait`.  
  
```cpp  
  
// Using a tile_static memory fence.  
parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),  
     [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)   
{  
    // Copy the values of the tile into a tile-sized array.  
    tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];  
    tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];  
  
    // Wait for the tile-sized array to load before calculating the average.  
    t_idx.barrier.wait_with_tile_static_memory_fence();  
  
    // If you remove the if statement, then the calculation executes for every  
    // thread in the tile, and makes the same assignment to averages each time.  
    if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {  
        for (int trow = 0; trow < SAMPLESIZE; trow++) {  
            for (int tcol = 0; tcol < SAMPLESIZE; tcol++) {  
                averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];  
            }  
        }  
        averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);  
    }  
});  
  
```  
  
## См. также  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Ключевое слово tile\_static](../Topic/tile_static%20Keyword.md)