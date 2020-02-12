---
title: Использование плиток
ms.date: 11/19/2018
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
ms.openlocfilehash: e5cedde255846f61ed0aaadacbd9966c00a03c9d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126270"
---
# <a name="using-tiles"></a>Использование плиток

Чтобы максимально увеличить ускорение приложения, можно использовать мозаичное заполнение. Мозаичное заполнение разделяет потоки на равные прямоугольные подмножества или *плитки*. Если вы используете подходящий размер плитки и алгоритм мозаичного заполнения, вы можете получить еще больше возможностей ускорения от кода C++ amp. Основные компоненты мозаичного заполнения:

- `tile_static` переменные. Основное преимущество мозаичного использования — повышение производительности от `tile_static`ного доступа. Доступ к данным в `tile_static` памяти может выполняться значительно быстрее, чем доступ к данным в глобальном пространстве (`array` или объекты `array_view`). Экземпляр `tile_static` переменной создается для каждой плитки, а все потоки в плитке имеют доступ к переменной. В типичном алгоритме мозаичного заполнения данные копируются в `tile_static`ную память один раз из глобальной памяти, а затем обращаются к ним много раз из памяти `tile_static`.

- [метод tile_barrier:: wait](reference/tile-barrier-class.md#wait). Вызов `tile_barrier::wait` приостанавливает выполнение текущего потока до тех пор, пока все потоки в этой плитке не будут обращаться к `tile_barrier::wait`. Нельзя гарантировать порядок, в котором будут выполняться потоки, но только те потоки, которые не будут выполняться после вызова `tile_barrier::wait` до тех пор, пока все потоки не достигают вызова. Это означает, что с помощью метода `tile_barrier::wait` можно выполнять задачи на мозаичном уровне, а не на основе потоков. Типичный алгоритм заполнения содержит код для инициализации `tile_static` памяти для всей плитки, за которой следует вызов `tile_barrier::wait`. Следующий код `tile_barrier::wait` содержит вычисления, требующие доступа ко всем значениям `tile_static`.

- Локальное и глобальное индексирование. У вас есть доступ к индексу потока относительно всего `array_view` или `array` объекта и индекса относительно плитки. Использование локального индекса может облегчить чтение и отладку кода. Как правило, для доступа к переменным `tile_static` используется локальное индексирование, а для доступа к переменным `array` и `array_view` — глобальное индексирование.

- класс [tiled_extent](../../parallel/amp/reference/tiled-extent-class.md) и [tiled_index](../../parallel/amp/reference/tiled-index-class.md). Вместо объекта `extent` в вызове `parallel_for_each` используется объект `tiled_extent`. Вместо объекта `index` в вызове `parallel_for_each` используется объект `tiled_index`.

Чтобы воспользоваться преимуществами мозаичного заполнения, алгоритм должен секционировать домен вычислений на плитки, а затем копировать данные плитки в `tile_static` переменные для ускорения доступа.

## <a name="example-of-global-tile-and-local-indices"></a>Пример глобальных, мозаичных и локальных индексов

На следующей диаграмме представлена 8x9 матрица данных, упорядоченная в плитках 2.

![&#45;матрица&#45;с 8 по 9,&#45;разделенная на 2 на&#45;3 плитки](../../parallel/amp/media/usingtilesmatrix.png "&#45;матрица&#45;с 8 по 9,&#45;разделенная на 2 на&#45;3 плитки")

В следующем примере выводятся глобальные, мозаичные и локальные индексы этой мозаичной матрицы. Объект `array_view` создается с помощью элементов типа `Description`. `Description` содержит глобальные и локальные индексы элемента в матрице. Код в вызове `parallel_for_each` задает значения глобальных, мозаичных и локальных индексов каждого элемента. Выходные данные отображают значения в структурах `Description`.

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

int main() {
    TilingDescription();
    char wait;
    std::cin >> wait;
}
```

Основная работа примера находится в определении объекта `array_view` и вызове `parallel_for_each`.

1. Вектор структур `Description` копируется в объект `array_view` 8x9.

2. Метод `parallel_for_each` вызывается с объектом `tiled_extent` в качестве домена вычислений. Объект `tiled_extent` создается путем вызова метода `extent::tile()` переменной `descriptions`. Параметры типа вызова `extent::tile()`, `<2,3>`, указывают, что создаются плитки 2. Таким же 8x9 матрица мозаично заполняет 12 плиток, четыре строки и три столбца.

3. Метод `parallel_for_each` вызывается с помощью объекта `tiled_index<2,3>` (`t_idx`) в качестве индекса. Параметры типа индекса (`t_idx`) должны соответствовать параметрам типа домена вычислений (`descriptions.extent.tile< 2, 3>()`).

4. При выполнении каждого потока индекс `t_idx` возвращает сведения о том, в какой плитке находится поток (`tiled_index::tile` свойство), и расположение потока в плитке (свойство`tiled_index::local`).

## <a name="tile-synchronizationtile_static-and-tile_barrierwait"></a>Синхронизация плитки — tile_static и tile_barrier:: wait

В предыдущем примере показан макет плитки и индексы, но это не очень полезно.  Мозаичное заполнение может оказаться полезным, когда плитки являются неотъемлемой частью алгоритма и используют `tile_static` переменные. Поскольку все потоки в плитке имеют доступ к `tile_static` переменным, вызовы `tile_barrier::wait` используются для синхронизации доступа к переменным `tile_static`. Несмотря на то, что все потоки в плитке имеют доступ к `tile_static` переменным, нет гарантированного порядка выполнения потоков в плитке. В следующем примере показано, как использовать переменные `tile_static` и метод `tile_barrier::wait` для вычисления среднего значения каждой плитки. Ниже приведены ключевые сведения о примере.

1. RawData хранится в матрице 8x8.

2. Размер плитки — 2x2. При этом создается сетка 4x4 для плиток, а средние значения могут храниться в матрице 4x4 с помощью объекта `array`. Существует только ограниченное число типов, которые можно записать по ссылке в функции, ограниченной AMP. Класс `array` является одним из них.

3. Размер матрицы и размер выборки определяются с помощью `#define` инструкций, так как параметры типа для `array`, `array_view`, `extent`и `tiled_index` должны быть постоянными значениями. Можно также использовать объявления `const int static`. В качестве дополнительного преимущества можно изменить размер выборки, чтобы вычислить среднюю плитку 4x4.

4. `tile_static` массив 2x2 значений float объявляется для каждой плитки. Хотя объявление находится в пути кода для каждого потока, для каждой плитки в матрице создается только один массив.

5. Существует строка кода для копирования значений в каждой плитке в массив `tile_static`. Для каждого потока после копирования значения в массив выполнение в потоке останавливается из-за вызова `tile_barrier::wait`.

6. Когда все потоки в плитке достигли барьера, среднее можно вычислить. Поскольку код выполняется для каждого потока, существует оператор `if` для вычисления среднего только в одном потоке. Среднее значение хранится в переменной средних значений. Барьер по сути является конструкцией, которая управляет вычислениями мозаикой, так же, как вы можете использовать цикл `for`.

7. Данные в переменной `averages`, так как это `array` объект, необходимо скопировать обратно на узел. В этом примере используется оператор векторного преобразования.

8. В полном примере можно изменить SAMPLESIZE на 4, и код будет выполняться правильно без каких бы то ни было изменений.

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
    // Output for SAMPLESIZE = 2 is:
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

Может возникнуть желание создать переменную `tile_static` с именем `total` и увеличить эту переменную для каждого потока следующим образом:

```cpp
// Do not do this.
tile_static float total;
total += matrix[t_idx];
t_idx.barrier.wait();

averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);
```

Первая проблема с этим подходом заключается в том, что `tile_static` переменные не могут иметь инициализаторы. Вторая проблема заключается в том, что для назначения `total`существует условие гонки, так как все потоки в плитке имеют доступ к переменной без определенного порядка. Можно программировать алгоритм, чтобы только один поток мог получить доступ к общему количеству в каждом барьере, как показано далее. Однако это решение не является расширяемым.

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

## <a name="memory-fences"></a>Границы памяти

Существует два типа доступа к памяти, которые должны быть синхронизированы — глобальный доступ к памяти и `tile_static` доступ к памяти. Объект `concurrency::array` выделяет только глобальную память. `concurrency::array_view` может ссылаться на глобальную память, `tile_static`ную память или и то, и другое, в зависимости от того, как она была построена.  Существует два типа памяти, которые необходимо синхронизировать:

- глобальная память

- `tile_static`

*Ограждение памяти* гарантирует, что доступ к памяти будет доступен другим потокам в плитке потока, и что доступ к памяти выполняется в соответствии с порядком программы. Чтобы убедиться в этом, компиляторы и процессоры не переупорядочивают операции чтения и записи через ограждение. В C++ amp граница памяти создается путем вызова одного из следующих методов:

- [метод tile_barrier:: wait](reference/tile-barrier-class.md#wait): создает ограждение вокруг глобальной и `tile_static` памяти.

- [метод tile_barrier:: wait_with_all_memory_fence](reference/tile-barrier-class.md#wait_with_all_memory_fence): создает ограждение вокруг глобальной и `tile_static` памяти.

- [метод tile_barrier:: wait_with_global_memory_fence](reference/tile-barrier-class.md#wait_with_global_memory_fence): создает ограждение только для глобальной памяти.

- [метод tile_barrier:: wait_with_tile_static_memory_fence](reference/tile-barrier-class.md#wait_with_tile_static_memory_fence): создает ограждение только для `tile_static` памяти.

Вызов конкретной ограждения может повысить производительность приложения. Тип барьера влияет на то, как компилятор и инструкции по переупорядочению оборудования. Например, если используется глобальная граница памяти, она применяется только к глобальным доступам к памяти, поэтому компилятор и оборудование могут переупорядочивать операции чтения и записи в `tile_static` переменных на двух сторонах ограждения.

В следующем примере барьер синхронизирует операции записи с `tileValues`, `tile_static` переменной. В этом примере `tile_barrier::wait_with_tile_static_memory_fence` вызывается вместо `tile_barrier::wait`.

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

## <a name="see-also"></a>См. также раздел

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Ключевое слово tile_static](../../cpp/tile-static-keyword.md)
