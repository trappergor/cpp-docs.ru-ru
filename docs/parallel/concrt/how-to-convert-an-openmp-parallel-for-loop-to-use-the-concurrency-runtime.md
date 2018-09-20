---
title: 'Практическое: преобразование параллельного цикла для использования среды выполнения с параллелизмом for OpenMP | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5295a7e38ef511cd2703961ffe8fe6f22faa74ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407963"
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>Практическое руководство. Преобразование параллельного цикла for OpenMP для использования среды выполнения с параллелизмом

В этом примере показано, как преобразовать простой цикл, использует OpenMP [параллельных](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) и [для](../../parallel/openmp/reference/for-openmp.md) директивы для использования среды выполнения с параллелизмом [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм.

## <a name="example"></a>Пример

В этом примере использует OpenMP и среда выполнения с параллелизмом для вычисления количества простых чисел в массив случайных значений.

[!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]

В этом примере формируются следующие данные:

```Output
Using OpenMP...
found 107254 prime numbers.
Using the Concurrency Runtime...
found 107254 prime numbers.
```

`parallel_for` Алгоритм и OpenMP 3.0 позволяют тип индекса быть целочисленным типом со знаком или без знака целочисленный тип. `parallel_for` Алгоритм также гарантирует, что указанный диапазон не вызывает переполнения тип со знаком. OpenMP версий 2.0 и 2.5 позволяют со знаком только целочисленные типы индекса. OpenMP также не выполняет проверку диапазона индекса.

Версию этого примера, который использует среда выполнения с параллелизмом также использует [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) объекта вместо [atomic](../../parallel/openmp/reference/atomic.md) директиву, чтобы увеличить значение счетчика без необходимости синхронизация.

Дополнительные сведения о `parallel_for` и другие параллельные алгоритмы, см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md). Дополнительные сведения о `combinable` , представлена в разделе [параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="example"></a>Пример

В этом примере изменяется предыдущий реагировать на [std::array](../../standard-library/array-class-stl.md) вместо объекта с собственным массивом. OpenMP версий 2.0 и 2.5 допускает для подписанных целочисленные типы индекса только в `parallel_for` конструкция, нельзя использовать итераторы для доступа к элементам контейнера стандартной библиотеки C++ в параллельном режиме. Библиотека параллельных шаблонов (PPL) предоставляет [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм, который выполняет задачи в параллельном режиме, в итеративном контейнере вроде предоставленных стандартной библиотеки C++. Он использует ту же логику секционирования, `parallel_for` алгоритмом. `parallel_for_each` Алгоритм напоминает стандартной библиотеки C++ [std::for_each](../../standard-library/algorithm-functions.md#for_each) алгоритм, за исключением случаев, `parallel_for_each` алгоритм выполняет задачи параллельно.

[!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `concrt-omp-count-primes.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**CL.exe/EHsc/OpenMP concrt-omp-count-primes.cpp**

## <a name="see-also"></a>См. также

[Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)

