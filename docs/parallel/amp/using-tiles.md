---
title: Использование плиток
ms.date: 11/19/2018
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
ms.openlocfilehash: edef9154b0c4da6f53c8ac40ee84e55e9b38a9b7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228470"
---
# <a name="using-tiles"></a>Использование плиток

Чтобы максимально увеличить ускорение приложения, можно использовать мозаичное заполнение. Мозаичное заполнение разделяет потоки на равные прямоугольные подмножества или *плитки*. Если вы используете подходящий размер плитки и алгоритм мозаичного заполнения, вы можете получить еще более ускорение от C++ AMPного кода. Основные компоненты мозаичного заполнения:

- `tile_static`среды. Основное преимущество мозаичного использования — это выигрыш в производительности от `tile_static` доступа. Доступ к данным в `tile_static` памяти может быть значительно быстрее, чем доступ к данным в глобальном пространстве ( `array` или `array_view` объектах). Экземпляр `tile_static` переменной создается для каждой плитки, а все потоки в плитке имеют доступ к переменной. В типичном алгоритме мозаичного заполнения данные копируются в `tile_static` память один раз из глобальной памяти, а затем обращаются к памяти много раз `tile_static` .

- [метод tile_barrier:: wait](reference/tile-barrier-class.md#wait). Вызов метода `tile_barrier::wait` приостанавливает выполнение текущего потока до тех пор, пока все потоки в той же плитке не будут обращаться к вызову `tile_barrier::wait` . Нельзя гарантировать порядок, в котором будут выполняться потоки, но только те потоки, которые находятся в плитке, не будут выполняться после вызова `tile_barrier::wait` до тех пор, пока все потоки не достигают вызова. Это означает, что с помощью `tile_barrier::wait` метода можно выполнять задачи на мозаичном уровне, а не на основе потоков. Типичный алгоритм заполнения содержит код для инициализации `tile_static` памяти для всей плитки, за которой следует вызов `tile_barrier::wait` . Следующий код `tile_barrier::wait` содержит вычисления, для которых требуется доступ ко всем `tile_static` значениям.

- Локальное и глобальное индексирование. У вас есть доступ к индексу потока относительно всего `array_view` `array` объекта или и индекса относительно плитки. Использование локального индекса может облегчить чтение и отладку кода. Как правило, для доступа к переменным используется локальное индексирование `tile_static` , а для доступа к переменным — глобальное индексирование `array` `array_view` .

- класс [tiled_extent](../../parallel/amp/reference/tiled-extent-class.md) и [tiled_index](../../parallel/amp/reference/tiled-index-class.md). `tiled_extent`Вместо `extent` объекта в `parallel_for_each` вызове используется объект. `tiled_index`Вместо `index` объекта в `parallel_for_each` вызове используется объект.

Чтобы воспользоваться преимуществами мозаичного заполнения, алгоритм должен секционировать домен вычислений на плитки, а затем копировать данные плитки в `tile_static` переменные для более быстрого доступа.

## <a name="example-of-global-tile-and-local-indices"></a>Пример глобальных, мозаичных и локальных индексов

На следующей диаграмме представлена 8x9 матрица данных, упорядоченная в плитках 2.

![8&#45;матрица&#45;9, разделенная на 2&#45;по&#45;3 плитки](../../parallel/amp/media/usingtilesmatrix.png "8&#45;матрица&#45;9, разделенная на 2&#45;по&#45;3 плитки")

В следующем примере выводятся глобальные, мозаичные и локальные индексы этой мозаичной матрицы. `array_view`Объект создается с помощью элементов типа `Description` . `Description`Содержит глобальные, мозаичные и локальные индексы элемента в матрице. Код в вызове `parallel_for_each` задает значения глобальных, мозаичных и локальных индексов каждого элемента. Выходные данные отображают значения в `Description` структурах.

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

Основная работа примера находится в определении `array_view` объекта и вызове `parallel_for_each` .

1. Вектор `Description` структур копируется в `array_view` объект 8x9.

2. `parallel_for_each`Метод вызывается с объектом в `tiled_extent` качестве домена вычислений. `tiled_extent`Объект создается путем вызова `extent::tile()` метода `descriptions` переменной. Параметры типа вызова `extent::tile()` , `<2,3>` , указывают, что 2 плитки создаются. Таким же 8x9 матрица мозаично заполняет 12 плиток, четыре строки и три столбца.

3. `parallel_for_each`Метод вызывается с помощью `tiled_index<2,3>` объекта () в `t_idx` качестве индекса. Параметры типа индекса ( `t_idx` ) должны соответствовать параметрам типа в домене вычислений ( `descriptions.extent.tile< 2, 3>()` ).

4. При выполнении каждого потока индекс `t_idx` возвращает сведения о том, в какой плитке находится поток ( `tiled_index::tile` свойство), и расположение потока внутри плитки ( `tiled_index::local` свойство).

## <a name="tile-synchronizationtile_static-and-tile_barrierwait"></a>Синхронизация плитки — tile_static и tile_barrier:: wait

В предыдущем примере показан макет плитки и индексы, но это не очень полезно.  Мозаичное заполнение может оказаться полезным, когда плитки являются неотъемлемой частью алгоритма и переменных эксплойта `tile_static` . Поскольку все потоки в плитке имеют доступ к `tile_static` переменным, для `tile_barrier::wait` синхронизации доступа к переменным используются вызовы метода `tile_static` . Хотя все потоки в плитке имеют доступ к `tile_static` переменным, в плитке нет гарантированно определенного порядка выполнения потоков. В следующем примере показано, как использовать `tile_static` переменные и `tile_barrier::wait` метод для вычисления среднего значения каждой плитки. Ниже приведены ключевые сведения о примере.

1. RawData хранится в матрице 8x8.

2. Размер плитки — 2x2. При этом создается сетка 4x4 для плиток, а средние значения могут храниться в матрице 4x4 с помощью `array` объекта. Существует только ограниченное число типов, которые можно записать по ссылке в функции, ограниченной AMP. `array`Класс является одним из них.

3. Размер матрицы и размер выборки определяются `#define` операторами using, так как параметры типа для `array` , `array_view` , `extent` и `tiled_index` должны быть константными значениями. Также можно использовать `const int static` объявления. В качестве дополнительного преимущества можно изменить размер выборки, чтобы вычислить среднюю плитку 4x4.

4. `tile_static`Массив 2x2 значений float объявляется для каждой плитки. Хотя объявление находится в пути кода для каждого потока, для каждой плитки в матрице создается только один массив.

5. Существует строка кода для копирования значений в каждой плитке в `tile_static` массив. Для каждого потока после копирования значения в массив выполнение в потоке останавливается из-за вызова `tile_barrier::wait` .

6. Когда все потоки в плитке достигли барьера, среднее можно вычислить. Поскольку код выполняется для каждого потока, существует `if` оператор для вычисления среднего только в одном потоке. Среднее значение хранится в переменной средних значений. Барьер по сути является конструкцией, которая управляет вычислениями мозаикой, так же, как можно использовать **`for`** цикл.

7. Данные в `averages` переменной, поскольку это `array` объект, должны быть скопированы обратно на узел. В этом примере используется оператор векторного преобразования.

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

Может возникнуть желание создать `tile_static` переменную с именем `total` и увеличить эту переменную для каждого потока следующим образом:

```cpp
// Do not do this.
tile_static float total;
total += matrix[t_idx];
t_idx.barrier.wait();

averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);
```

Первая проблема с этим подходом заключается в том, что `tile_static` переменные не могут иметь инициализаторы. Вторая проблема заключается в том, что существует условие состязания для назначения `total` , так как все потоки в плитке имеют доступ к переменной без определенного порядка. Можно программировать алгоритм, чтобы только один поток мог получить доступ к общему количеству в каждом барьере, как показано далее. Однако это решение не является расширяемым.

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

Существует два типа доступа к памяти, которые должны быть синхронизированы — глобальный доступ к памяти и `tile_static` доступ к памяти. `concurrency::array`Объект выделяет только глобальную память. `concurrency::array_view`Может ссылаться на глобальную память, `tile_static` память или и то, и другое, в зависимости от того, как она была построена.  Существует два типа памяти, которые необходимо синхронизировать:

- глобальная память

- `tile_static`

*Ограждение памяти* гарантирует, что доступ к памяти будет доступен другим потокам в плитке потока, и что доступ к памяти выполняется в соответствии с порядком программы. Чтобы убедиться в этом, компиляторы и процессоры не переупорядочивают операции чтения и записи через ограждение. В C++ AMP граница памяти создается путем вызова одного из следующих методов:

- [метод tile_barrier:: wait](reference/tile-barrier-class.md#wait): создает ограждение вокруг глобальной и `tile_static` памяти.

- [метод tile_barrier:: wait_with_all_memory_fence](reference/tile-barrier-class.md#wait_with_all_memory_fence): создает ограждение вокруг глобальной и `tile_static` памяти.

- [метод tile_barrier:: wait_with_global_memory_fence](reference/tile-barrier-class.md#wait_with_global_memory_fence): создает ограждение только для глобальной памяти.

- [метод tile_barrier:: wait_with_tile_static_memory_fence](reference/tile-barrier-class.md#wait_with_tile_static_memory_fence): создает ограждение только для `tile_static` памяти.

Вызов конкретной ограждения может повысить производительность приложения. Тип барьера влияет на то, как компилятор и инструкции по переупорядочению оборудования. Например, если используется глобальная граница памяти, она применяется только к глобальным доступам к памяти, поэтому компилятор и оборудование могут переупорядочивать операции чтения и записи в `tile_static` переменные на двух сторонах ограждения.

В следующем примере барьер синхронизирует операции записи с `tileValues` `tile_static` переменной. В этом примере `tile_barrier::wait_with_tile_static_memory_fence` вызывается вместо `tile_barrier::wait` .

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

## <a name="see-also"></a>См. также статью

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Ключевое слово tile_static](../../cpp/tile-static-keyword.md)
