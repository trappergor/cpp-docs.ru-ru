---
title: Ключевое слово tile_static
ms.date: 11/04/2016
f1_keywords:
- tile_static_CPP
helpviewer_keywords:
- tile_static keyword
ms.assetid: d78384d4-65d9-45cf-b3df-7e904f489d06
ms.openlocfilehash: 1e0e967edd1808b27d3d4e92f29f7472608f8e65
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588166"
---
# <a name="tilestatic-keyword"></a>Ключевое слово tile_static

**Tile_static** ключевое слово используется для объявления переменной, доступный всем потокам в мозаике потоков. Время существования переменной начинается, когда при выполнении достигается точка объявления, и завершается при возврате из функции ядра. Дополнительные сведения об использовании мозаик см. в разделе [с помощью плитки](../parallel/amp/using-tiles.md).

**Tile_static** ключевое слово имеет следующие ограничения:

- Его можно использовать только для переменных, находящихся в функции с модификатором `restrict(amp)`.

- Не допускается его использование для переменных, являющихся указателями или ссылочными типами.

- Объект **tile_static** переменной не может иметь инициализатор. Конструкторы и деструкторы по умолчанию не вызываются автоматически.

- Значение неинициализированной **tile_static** переменная не определена.

- Если **tile_static** переменная объявлена в графе вызовов, корень которого находится с помощью вызова не использующем мозаику `parallel_for_each`, выдается предупреждение и поведение переменной не определено.

## <a name="example"></a>Пример

В следующем примере показан как **tile_static** переменная может использоваться для накопления данных из нескольких потоков в плитке.

```cpp
// Sample data:
int sampledata[] = {
    2, 2, 9, 7, 1, 4,
    4, 4, 8, 8, 3, 4,
    1, 5, 1, 2, 5, 2,
    6, 8, 3, 2, 7, 2};

// The tiles:
// 2 2    9 7    1 4
// 4 4    8 8    3 4
//
// 1 5    1 2    5 2
// 6 8    3 2    7 2

// Averages:
int averagedata[] = {
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
};

array_view<int, 2> sample(4, 6, sampledata);
array_view<int, 2> average(4, 6, averagedata);

parallel_for_each(
    // Create threads for sample.extent and divide the extent into 2 x 2 tiles.
    sample.extent.tile<2,2>(),
    [=](tiled_index<2,2> idx) restrict(amp)
    {
        // Create a 2 x 2 array to hold the values in this tile.
        tile_static int nums[2][2];
        // Copy the values for the tile into the 2 x 2 array.
        nums[idx.local[1]][idx.local[0]] = sample[idx.global];
        // When all the threads have executed and the 2 x 2 array is complete, find the average.
        idx.barrier.wait();
        int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1];
        // Copy the average into the array_view.
        average[idx.global] = sum / 4;
      }
);

for (int i = 0; i < 4; i++) {
    for (int j = 0; j < 6; j++) {
        std::cout << average(i,j) << " ";
    }
    std::cout << "\n";
}

// Output:
// 3 3 8 8 3 3
// 3 3 8 8 3 3
// 5 5 2 2 4 4
// 5 5 2 2 4 4
// Sample data.
int sampledata[] = {
    2, 2, 9, 7, 1, 4,
    4, 4, 8, 8, 3, 4,
    1, 5, 1, 2, 5, 2,
    6, 8, 3, 2, 7, 2};

// The tiles are:
// 2 2    9 7    1 4
// 4 4    8 8    3 4
//
// 1 5    1 2    5 2
// 6 8    3 2    7 2

// Averages.
int averagedata[] = {
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
};

array_view<int, 2> sample(4, 6, sampledata);
array_view<int, 2> average(4, 6, averagedata);

parallel_for_each(
    // Create threads for sample.grid and divide the grid into 2 x 2 tiles.
    sample.extent.tile<2,2>(),
    [=](tiled_index<2,2> idx) restrict(amp)
    {
        // Create a 2 x 2 array to hold the values in this tile.
        tile_static int nums[2][2];
        // Copy the values for the tile into the 2 x 2 array.
        nums[idx.local[1]][idx.local[0]] = sample[idx.global];
        // When all the threads have executed and the 2 x 2 array is complete, find the average.
        idx.barrier.wait();
        int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1];
        // Copy the average into the array_view.
        average[idx.global] = sum / 4;
      }
);

for (int i = 0; i < 4; i++) {
    for (int j = 0; j < 6; j++) {
        std::cout << average(i,j) << " ";
    }
    std::cout << "\n";
}

// Output.
// 3 3 8 8 3 3
// 3 3 8 8 3 3
// 5 5 2 2 4 4
// 5 5 2 2 4 4
```

## <a name="see-also"></a>См. также

[Модификаторы, используемые в системах Майкрософт](../cpp/microsoft-specific-modifiers.md)<br/>
[Общие сведения о C++ AMP](../parallel/amp/cpp-amp-overview.md)<br/>
[parallel_for_each функции (C++ AMP)](../parallel/amp/reference/concurrency-namespace-functions-amp.md#parallel_for_each)<br/>
[Пошаговое руководство. Умножение матриц](../parallel/amp/walkthrough-matrix-multiplication.md)