---
title: С помощью плитки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4e3d1e37562e9e14bbbeda5a01198358b4615d3c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="using-tiles"></a>Использование плиток
Мозаичное заполнение можно использовать для увеличения расстояния, ваше приложение. Мозаичное заполнение делит потоков равно прямоугольный подмножества или *плитки*. При использовании плитки соответствующий размер и Мозаичная алгоритм, можно получить еще больше ускорение в коде C++ AMP. Ниже перечислены основные компоненты мозаичное заполнение  
  
- `tile_static` Переменные. Основным преимуществом мозаичное заполнение является увеличение производительности благодаря `tile_static` доступа. Доступ к данным в `tile_static` память может быть значительно быстрее, чем доступ к данным в глобальном пространстве (`array` или `array_view` объектов). Экземпляр `tile_static` переменная создается для каждого мозаичного элемента, и все потоки в плитке имеют доступ к переменной. В алгоритме типичные мозаики, данные копируются в `tile_static` память один раз из глобальной памяти и затем доступных много раз из `tile_static` памяти.  
  
- [Метод tile_barrier::wait](reference/tile-barrier-class.md#wait). Вызов `tile_barrier::wait` приостанавливает выполнение текущего потока, пока все потоки на плитке же достигнут вызов `tile_barrier::wait`. Не гарантирует порядок запуска потоков, только то, что нет потоков на плитке будет выполняться после вызова метода `tile_barrier::wait` пока все потоки достигнут вызова. Это означает, что с помощью `tile_barrier::wait` метод, можно выполнять задачи на основой плитки, плитки, а не отдельного поток. Алгоритм мозаичное заполнение обычно содержит код для инициализации `tile_static` память для всей мозаики, а затем с помощью вызова `tile_barrer::wait`. Код, следующий за `tile_barrier::wait` содержит вычисления, которые требуется доступ ко всем `tile_static` значения.  

  
-   Локальные и глобальные индексирования. У вас есть доступ к индексу потока относительно всего `array_view` или `array` объектов и индексов относительно плитки. С помощью локального индекса может сделать код проще читать и отладки. Обычно используется локальный индексирования для доступа к `tile_static` переменных и глобальных индексирование доступа `array` и `array_view` переменных.  
  
- [Класс tiled_extent](../../parallel/amp/reference/tiled-extent-class.md) и [класс tiled_index](../../parallel/amp/reference/tiled-index-class.md). Вы используете `tiled_extent` объекта вместо `extent` объекта в `parallel_for_each` вызова. Вы используете `tiled_index` объекта вместо `index` объекта в `parallel_for_each` вызова.  
  
 Чтобы воспользоваться преимуществами мозаичное заполнение, ваш алгоритм необходимо секционировать домене вычислений на плитки, а затем скопировать данные плитки в `tile_static` переменные для более быстрого доступа.  
  
## <a name="example-of-global-tile-and-local-indices"></a>Пример глобального, Плитка и локальных индексов  
 Следующая диаграмма представляет данные, которые организованы в плитки 2 x 3 матрица 8 x 9.  
  
 ![8&#45;по&#45;9 матрица разделенная на 2&#45;по&#45;3 плитки](../../parallel/amp/media/usingtilesmatrix.png "usingtilesmatrix")  
  
 В следующем примере показаны глобальные, плитки, и локальный индексы мозаикой матрицы. `array_view` Объект создается с помощью элементов типа `Description`. `Description` Содержит глобальные, Плитка и локальных индексы элемента в матрице. Код в вызов `parallel_for_each` задает значения глобального, плитки и локального индексы каждого элемента. Выходные данные будут содержать значения в `Description` структуры.  
  
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
    int colorValue = (color == 0)  4 : 2;  
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
  
 Является основной рабочей примера в определении `array_view` объект и вызова `parallel_for_each`.  
  
1.  Вектор `Description` структуры копируется в 8 x 9 `array_view` объекта.  
  
2.  `parallel_for_each` Метод вызывается с `tiled_extent` объект как домене вычислений. `tiled_extent` Создается путем вызова `extent::tile()` метод `descriptions` переменной. Параметры типа вызова `extent::tile()`, `<2,3>`, укажите, что создаются плитки 2 x 3. Таким образом матрица 8 x 9 накладывается на 12 плитки, четыре строки и три столбца.  
  
3.  `parallel_for_each` Вызывать метод с помощью `tiled_index<2,3>` объекта (`t_idx`) как индекс. Параметры типа индекса (`t_idx`) должны совпадать с параметрами типа вычислений домена (`descriptions.extent.tile< 2, 3>()`).  
  
4.  При выполнении каждого потока, индекс `t_idx` возвращает сведения о какой плитки поток находится в (`tiled_index::tile` свойства) и положение потока фрагмента (`tiled_index::local` свойство).  
  
## <a name="tile-synchronizationtilestatic-and-tilebarrierwait"></a>Плитки синхронизации — tile_static и tile_barrier::wait  
 Предыдущий пример иллюстрирует мозаичного макета и индексы, но не сам по себе очень полезным.  Мозаичное заполнение оказывается полезным, когда плитки являются неотъемлемой частью алгоритма и воспользоваться `tile_static` переменных. Так как все потоки в плитке доступ `tile_static` переменных, вызовы `tile_barrier::wait` используются для синхронизации доступа к `tile_static` переменных. Несмотря на то, что все потоки в плитке имеют доступ к `tile_static` переменные, нет гарантированного порядка выполнения потоков на плитке. В следующем примере показано, как использовать `tile_static` переменных и `tile_barrier::wait` метод, чтобы вычислить среднее значение каждого элемента мозаики. Ниже приведены основные сведения о примере с помощью клавиш.  
  
1.  RawData хранятся в матрице 8 x 8.  
  
2.  Размер мозаики — 2 x 2. Эта команда создает сетку 4 x 4 плиток и средние значения могут храниться в матрицу 4 x 4 с помощью `array` объекта. Существует ограниченное число типов, которые могут быть получены по ссылке в функции со спецификатором ограничения AMP. `array` Класс является одной из них.  
  
3.  Размер матрицы и размер выборки определяются с помощью `#define` инструкции, так как параметры типа, чтобы `array`, `array_view`, `extent`, и `tiled_index` должны быть константами. Можно также использовать `const int static` объявления. В качестве дополнительного преимущества является тривиальным, чтобы изменить размер выборки для вычисления среднего плитки более чем 4 x 4.  
  
4.  Объект `tile_static` 2 x 2 массив значений с плавающей запятой, объявленный для каждого элемента мозаики. Несмотря на то, что объявление находится в пути к коду для каждого потока, только один массив создается для каждого элемента мозаики в матрице.  
  
5.  Строка кода для копирования значений для каждой плитки `tile_static` массива. Для каждого потока после значение копируется в массив, выполнение в потоке останавливается из-за вызова `tile_barrier::wait`.  
  
6.  Если все потоки в плитке достигли барьера, можно вычислить среднее значение. Поскольку код выполняется для каждого потока, `if` инструкцию, чтобы только вычисления среднего значения в одном потоке. Среднее значение сохраняется в переменной средние значения. Барьер — по существу конструкция, которая управляет вычисления, плитки, так же, как можно использовать `for` цикла.  
  
7.  Данные в `averages` переменной, так как это `array` объекта, необходимо скопировать на узел. В этом примере используется оператор преобразования вектор.  
  
8.  В следующем полном примере SAMPLESIZE можно изменить на 4 и выполняется правильно без других изменений.  
  
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
  
## <a name="race-conditions"></a>Конфликты  
 Может понадобиться создать `tile_static` переменную с именем `total` и увеличить значение этой переменной для каждого потока, следующим образом:  
  
```cpp  
// Do not do this.  
tile_static float total;  
total += matrix[t_idx];  
t_idx.barrier.wait();

averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);

 
```  
  
 Первая проблема этого подхода заключается в том `tile_static` переменные не могут содержаться инициализаторы. Вторая проблема — это состояние гонки на назначение `total`, так как все потоки в плитке имеют доступ к переменной в произвольном порядке. Удалось программируется алгоритм разрешать только один поток для доступа к общему в каждом барьера, как показано далее. Однако это решение не является расширяемым.  
  
```cpp  
// Do not do this.  
tile_static float total;  
if (t_idx.local[0] == 0&& t_idx.local[1] == 0) {  
    total = matrix[t_idx];  
}  
t_idx.barrier.wait();

 
if (t_idx.local[0] == 0&& t_idx.local[1] == 1) {  
    total += matrix[t_idx];  
}  
t_idx.barrier.wait();

 
// etc.  
 
```  
  
## <a name="memory-fences"></a>Барьеры памяти  
 Существует два вида обращений к памяти, которые необходимо синхронизировать, доступ к глобальной памяти и `tile_static` доступ к памяти. Объект `concurrency::array` объект выделяет только глобальной памяти. Объект `concurrency::array_view` могут ссылаться на глобальную память `tile_static` памяти (или оба) в зависимости от того, как он был создан.  Существует два вида памяти, который должен быть синхронизирован.  
  
-   Глобальная память  
  
- `tile_static`  
  
 Объект *барьером памяти* гарантирует, что память, доступ к доступны для других потоков в поток плитки и порядке программы выполняются обращений к памяти. Чтобы обеспечить это, компиляторы и процессоры не изменять порядок операций чтения и записи для границы. В C++ AMP барьер памяти создается путем вызова одного из следующих методов:  
  

- [Метод tile_barrier::wait](reference/tile-barrier-class.md#wait): создает граница вокруг оба глобальных и `tile_static` памяти.  
  
- [Метод tile_barrier::wait_with_all_memory_fence](reference/tile-barrier-class.md#wait_with_all_memory_fence): создает граница вокруг оба глобальных и `tile_static` памяти.  
  
- [Метод tile_barrier::wait_with_global_memory_fence](reference/tile-barrier-class.md#wait_with_global_memory_fence): создает граница вокруг только глобальной памяти.  
  
- [Метод tile_barrier::wait_with_tile_static_memory_fence](reference/tile-barrier-class.md#wait_with_tile_static_memory_fence): создает граница вокруг только `tile_static` памяти.  

  
 Вызов определенных граница, которой требуется может повысить производительность приложения. Тип барьера влияет как компилятор и оборудовании, изменение порядка операторов. Например, если использовать границы глобальной памяти, оно применяется доступ только к глобальной памяти и таким образом, компилятор и оборудования может изменить порядок считывает и записывает `tile_static` переменные на две стороны границы.  
  
 В следующем примере барьера синхронизирует операции записи `tileValues`, `tile_static` переменной. В этом примере `tile_barrier::wait_with_tile_static_memory_fence` вызывается вместо `tile_barrier::wait`.  
  
```cpp  
// Using a tile_static memory fence.  
parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),  
 [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)   
{ *// Copy the values of the tile into a tile-sized array.  
    tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];  
    tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];  
 *// Wait for the tile-sized array to load before calculating the average.  
    t_idx.barrier.wait_with_tile_static_memory_fence();

 *// If you remove the if statement, then the calculation executes for every *// thread in the tile, and makes the same assignment to averages each time.  
    if (t_idx.local[0] == 0&& t_idx.local[1] == 0) {  
    for (int trow = 0; trow <SAMPLESIZE; trow++) {  
    for (int tcol = 0; tcol <SAMPLESIZE; tcol++) {  
    averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];  
 }  
 }  
    averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);

 }  
});

 
```  
  
## <a name="see-also"></a>См. также  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Ключевое слово tile_static](../../cpp/tile-static-keyword.md)

