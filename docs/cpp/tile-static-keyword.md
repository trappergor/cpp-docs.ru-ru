---
title: Ключевое слово tile_static
ms.date: 11/04/2016
f1_keywords:
- tile_static_CPP
helpviewer_keywords:
- tile_static keyword
ms.assetid: d78384d4-65d9-45cf-b3df-7e904f489d06
ms.openlocfilehash: 9476c0c446463c04084f46ed17a8ada7fb01fd7e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188133"
---
# <a name="tile_static-keyword"></a>Ключевое слово tile_static

Ключевое слово **tile_static** используется для объявления переменной, к которой могут обращаться все потоки в плитке потоков. Время существования переменной начинается, когда при выполнении достигается точка объявления, и завершается при возврате из функции ядра. Дополнительные сведения об использовании плиток см. в разделе [использование плиток](../parallel/amp/using-tiles.md).

Ключевое слово **tile_static** имеет следующие ограничения.

- Его можно использовать только для переменных, находящихся в функции с модификатором `restrict(amp)`.

- Не допускается его использование для переменных, являющихся указателями или ссылочными типами.

- Переменная **tile_static** не может иметь инициализатор. Конструкторы и деструкторы по умолчанию не вызываются автоматически.

- Значение неинициализированной **tile_static** переменной не определено.

- Если переменная **tile_static** объявлена в графе вызовов, которая находится в корне с помощью немозаичного вызова для `parallel_for_each`, создается предупреждение и поведение переменной не определено.

## <a name="example"></a>Пример

В следующем примере показано, как можно использовать переменную **tile_static** для накопления данных по нескольким потокам в плитке.

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

## <a name="see-also"></a>См. также раздел

[Модификаторы, используемые в системах Майкрософт](../cpp/microsoft-specific-modifiers.md)<br/>
[Общие сведения о C++ AMP](../parallel/amp/cpp-amp-overview.md)<br/>
[Функция parallel_for_each (C++ amp)](../parallel/amp/reference/concurrency-namespace-functions-amp.md#parallel_for_each)<br/>
[Пошаговое руководство. Умножение матриц](../parallel/amp/walkthrough-matrix-multiplication.md)
