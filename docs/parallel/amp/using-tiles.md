---
title: Использование плиток | Документация Майкрософт
ms.custom: ''
ms.date: 06/28/2018
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
ms.openlocfilehash: df2f449cce01dc2d0903ff802ffb94914b68bceb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386272"
---
# <a name="using-tiles"></a>Использование плиток

Можно использовать заполнение плитками для максимального ускорения приложения. Заполнение плитками делит поток на равные прямоугольные подмножества или *плитки*. При использовании соответствующего размера мозаики и мозаичного алгоритма можно достичь еще большего ускорения в коде C++ AMP. Ниже приведены основные компоненты мозаичного заполнения.

- `tile_static` переменные. Основное преимущество мозаичного замощения — выигрыш в производительности от `tile_static` доступа. Доступ к данным в `tile_static` память может быть значительно быстрее, чем доступ к данным в глобальной области (`array` или `array_view` объектов). Экземпляр `tile_static` переменная создается для каждого элемента мозаики, и все потоки в мозаике имеют доступ к этой переменной. В типичном мозаичном алгоритме данные копируются в `tile_static` памяти сразу из глобальной памяти и затем будет обращаться много раз `tile_static` памяти.

- [Метод tile_barrier::wait](reference/tile-barrier-class.md#wait). Вызов `tile_barrier::wait` приостанавливает выполнение текущего потока, пока все потоки в одной плитке не достигнут вызова `tile_barrier::wait`. Не гарантирует порядок, в которые будут выполняться потоки, только то, что нет потоков в плитке не будет выполняться после вызова `tile_barrier::wait` пока все потоки достигнут этого вызова. Это означает, что с помощью `tile_barrier::wait` метод, можно выполнять задачи на плитку с плиткой, а не отдельного потоке. Типичный алгоритм мозаичного заполнения содержит код для инициализации `tile_static` памяти для всей мозаики, а затем с помощью вызова `tile_barrer::wait`. Код, который следует за `tile_barrier::wait` содержит вычисления, требующие доступа ко всем `tile_static` значения.

- Локальная и глобальная индексация. У вас есть доступ к индексу потока по отношению к всего `array_view` или `array` объекта и индексу относительно плитки. Использование локального индекса может сделать код проще читать и отлаживать. Как правило, используется локальное индексирование для доступа к `tile_static` переменных и глобальное индексирование для доступа к `array` и `array_view` переменные.

- [Класс tiled_extent](../../parallel/amp/reference/tiled-extent-class.md) и [класс tiled_index](../../parallel/amp/reference/tiled-index-class.md). Использовании `tiled_extent` вместо объекта `extent` объекта в `parallel_for_each` вызова. Использовании `tiled_index` вместо объекта `index` объекта в `parallel_for_each` вызова.

Чтобы воспользоваться преимуществами мозаичного замощения, ваш алгоритм должен разбить вычислительный домен на плитки и затем скопировать данные плиток в `tile_static` переменные для более быстрого доступа.

## <a name="example-of-global-tile-and-local-indices"></a>Пример глобального, мозаичного и локального индексов

Следующая схема представляет матрица 8 x 9 данные, которые расположены в плитки 2 x 3.

![8&#45;по&#45;матрицы 9 разделить на 2&#45;по&#45;3 плитки](../../parallel/amp/media/usingtilesmatrix.png "usingtilesmatrix")

В следующем примере показаны глобальные, мозаичные и локальные индексы в данной мозаичной матрице. `array_view` Объекта создается с помощью элементов типа `Description`. `Description` Содержит глобального, мозаичного и локального индексов элемента в матрице. Код в вызове `parallel_for_each` устанавливает значения глобального, мозаичного и локального индексов каждого элемента. В выходных данных отображаются значения в `Description` структуры.

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
    COORD coord;

    coord.X = width;
    coord.Y = height;
    SetConsoleScreenBufferSize(GetStdHandle(STD_OUTPUT_HANDLE), coord);

    SMALL_RECT* rect = new SMALL_RECT();
    rect->Left = 0;
    rect->Top = 0;
    rect->Right = width;
    rect->Bottom = height;
    SetConsoleWindowInfo(GetStdHandle(STD_OUTPUT_HANDLE), true, rect);
}

// This method creates an 8x9 matrix of Description structures.
// In the call to parallel_for_each, the structure is updated
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

Главная задача этого примера находится в определение `array_view` объекта и вызова `parallel_for_each`.

1. Вектор `Description` структур копируется в 8 x 9 `array_view` объекта.

2. `parallel_for_each` Метод вызывается с `tiled_extent` объект как вычислительный домен. `tiled_extent` Объекта создается путем вызова `extent::tile()` метод `descriptions` переменной. Параметры типа вызова `extent::tile()`, `<2,3>`, укажите, что создаются плитки 2 x 3. Таким образом матрица 8 x 9 разделена на 12 плиток, 4 строки и три столбца.

3. `parallel_for_each` Метод вызывается с помощью `tiled_index<2,3>` объекта (`t_idx`) как индекс. Параметры типа индекса (`t_idx`) должны соответствовать параметрам типов вычислительного домена (`descriptions.extent.tile< 2, 3>()`).

4. Когда каждый поток выполняется, индекс `t_idx` возвращает сведения о том, какой элемент потока в (`tiled_index::tile` свойства) и расположение потока внутри плитки (`tiled_index::local` свойство).

## <a name="tile-synchronizationtilestatic-and-tilebarrierwait"></a>Синхронизация плитки — tile_static и tile_barrier::wait

Предыдущий пример иллюстрирует структуру и индексы мозаики, но не само по себе очень полезно.  Заполнение плитками будет полезным, когда плитки встроены в алгоритм и используют `tile_static` переменные. Так как все потоки в мозаике имеют доступ к `tile_static` переменных, вызовы `tile_barrier::wait` используются для синхронизации доступа к `tile_static` переменные. Несмотря на то, что все потоки в мозаике имеют доступ к `tile_static` переменные, не существует гарантированного порядка выполнения потоков в плитке. В следующем примере показано, как использовать `tile_static` переменных и `tile_barrier::wait` метод, для которого требуется вычислить среднее значение каждого элемента мозаики. Ниже приведены основные положения для понимания примера:

1. Необработанные данные rawData хранятся в матрице 8 x 8.

2. Размер плитки — 2 x 2. Это создает сетку 4 x 4 из плиток и средние значения могут храниться в матрицу 4 x 4 с помощью `array` объекта. Существует только ограниченный набор типов, которые могут быть получены по ссылке в AMP-ограниченную функцию. `array` Класс является одной из них.

3. Размер матрицы и размер образца определяются с помощью `#define` инструкции, так как параметры типа, чтобы `array`, `array_view`, `extent`, и `tiled_index` должны быть константными значениями. Можно также использовать `const int static` объявления. Дополнительное преимущество является тривиальным, чтобы изменить размер выборки, для которого требуется вычислить среднее 4х4 плитки.

4. Объект `tile_static` объявленный для каждой плитки 2 x 2 массив значений с плавающей запятой. Несмотря на то, что объявление находится в пути кода для каждого потока, только один массив создается для каждого элемента мозаики в матрице.

5. Вот строка кода, чтобы скопировать нужные значения из каждой плитки `tile_static` массива. Для каждого потока после копирования значения в массив выполнение в потоке останавливается из-за вызова `tile_barrier::wait`.

6. Когда все потоки в мозаике достигли барьера, можно вычислить среднее значение. Поскольку код выполняется для каждого потока, `if` инструкции только вычисления среднего значения в одном потоке. Среднее значение хранится в переменной averages. Барьер — по существу конструкция, которая контролирует вычисления по плиткам, так же, как можно использовать `for` цикла.

7. Данные в `averages` переменной, так как это `array` объекта, необходимо скопировать на узел. В этом примере используется оператор преобразования вектора.

8. В следующем полном примере можно изменить значение SAMPLESIZE на 4 и код выполнится правильно без других изменений.

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

Было бы интересно создать `tile_static` переменную с именем `total` и увеличивать эту переменную для каждого потока, следующим образом:

```cpp
// Do not do this.
tile_static float total;
total += matrix[t_idx];
t_idx.barrier.wait();

averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);
```

Первая проблема этого подхода в том, что `tile_static` переменные не могут иметь инициализаторы. Вторая проблема — это гонки при присваивании `total`, так как все потоки в мозаике имеют доступ к переменной в произвольном порядке. Можно запрограммировать алгоритм так, чтобы разрешить только одному потоку для доступа к общему на каждом барьере, как показано далее. Тем не менее это решение не является расширяемым.

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

Существует два типа доступа к памяти, которые должны быть синхронизированы — доступ к глобальной памяти и `tile_static` доступ к памяти. Объект `concurrency::array` объект выделяет только глобальную память. Объект `concurrency::array_view` могут ссылаться на глобальную память `tile_static` памяти, или оба из них, в зависимости от того, как он был создан.  Существует два типа памяти, который должен быть синхронизирован.

- Глобальная память

- `tile_static`

Объект *барьер памяти* гарантирует, что доступ к памяти предоставляется для других потоков в плитке потоков и памяти доступы осуществляются в соответствии с порядком программы. Чтобы обеспечить это, компиляторы и процессоры не переупорядочивают чтения и записи через барьер. В C++ AMP барьер памяти создается путем вызова одного из этих методов:

- [Метод tile_barrier::wait](reference/tile-barrier-class.md#wait): создает барьер вокруг глобальной и `tile_static` памяти.

- [Метод tile_barrier::wait_with_all_memory_fence](reference/tile-barrier-class.md#wait_with_all_memory_fence): создает барьер вокруг глобальной и `tile_static` памяти.

- [Метод tile_barrier::wait_with_global_memory_fence](reference/tile-barrier-class.md#wait_with_global_memory_fence): создает барьер только вокруг глобальной памяти.

- [Метод tile_barrier::wait_with_tile_static_memory_fence](reference/tile-barrier-class.md#wait_with_tile_static_memory_fence): создает барьер только вокруг `tile_static` памяти.

Вызов конкретного барьера, которой требуется, можно повысить производительность приложения. Тип барьера влияет на том, как компилятор и оборудование переупорядочивает выражения. Например, при использовании барьера глобальной памяти, он применяется только к доступы к памяти и таким образом, компилятор и оборудование могут изменять порядок считывает и записывает `tile_static` переменные на обеих сторонах барьера.

В следующем примере барьер синхронизирует записи в `tileValues`, `tile_static` переменной. В этом примере `tile_barrier::wait_with_tile_static_memory_fence` вызывается вместо `tile_barrier::wait`.

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

    // If you remove the if statement, then the calculation executes
    // for every thread in the tile, and makes the same assignment to
    // averages each time.
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

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Ключевое слово tile_static](../../cpp/tile-static-keyword.md)
