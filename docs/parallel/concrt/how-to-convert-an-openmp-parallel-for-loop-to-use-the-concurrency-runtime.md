---
title: Практическое руководство. Преобразование параллельного цикла for OpenMP для использования среды выполнения с параллелизмом
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
ms.openlocfilehash: 4f523f9f6de7f1ffb4c3b578b60de587239dffb6
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507884"
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>Практическое руководство. Преобразование параллельного цикла for OpenMP для использования среды выполнения с параллелизмом

В этом примере показано, как преобразовать базовый цикл, использующий директивы OpenMP [Parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) и [for](../openmp/reference/openmp-directives.md#for-openmp) , для использования алгоритма среда выполнения с параллелизмом [Concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) .

## <a name="example---prime-count"></a>Пример — число простых

В этом примере используются OpenMP и среда выполнения с параллелизмом для вычисления числа простых чисел в массиве случайных значений.

[!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]

В этом примере формируются следующие данные:

```Output
Using OpenMP...
found 107254 prime numbers.
Using the Concurrency Runtime...
found 107254 prime numbers.
```

`parallel_for`Алгоритм и OpenMP 3,0 допускают, чтобы тип индекса был целочисленным типом со знаком или целочисленным типом без знака. `parallel_for`Алгоритм также гарантирует, что указанный диапазон не приведет к переполнению типа со знаком. В OpenMPх версий 2,0 и 2,5 допускается только для целочисленных типов индексов со знаком. OpenMP также не проверяет диапазон индексов.

Версия этого примера, в которой используется среда выполнения с параллелизмом, также использует объект [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) вместо директивы [Atomic](../openmp/reference/openmp-directives.md#atomic) для увеличения значения счетчика без необходимости синхронизации.

Дополнительные сведения о `parallel_for` и других параллельных алгоритмах см. в разделе [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md). Дополнительные сведения о `combinable` классе см. в разделе [Parallel Containers and Objects](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="example---use-stdarray"></a>Пример. использование std:: Array

В этом примере предыдущий объект изменяется для работы с объектом [std:: Array](../../standard-library/array-class-stl.md) , а не в собственном массиве. Поскольку OpenMP версий 2,0 и 2,5 допускают использование целочисленных типов индексов со знаком только в `parallel_for` конструкции, нельзя использовать итераторы для доступа к элементам контейнера стандартной библиотеки C++ параллельно. Библиотека параллельных шаблонов (PPL) предоставляет алгоритм [параллелизма::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) , который параллельно выполняет задачи в итеративном контейнере, например, предоставляемом стандартной библиотекой C++. Он использует ту же логику секционирования, которую `parallel_for` использует алгоритм. `parallel_for_each`Алгоритм напоминает алгоритм стандартной библиотеки C++ [std:: for_each](../../standard-library/algorithm-functions.md#for_each) , за исключением того, что `parallel_for_each` алгоритм выполняет задачи параллельно.

[!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем, `concrt-omp-count-primes.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc/OpenMP конкрт-ОМП-Каунт-примес. cpp**

## <a name="see-also"></a>См. также раздел

[Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)<br/>
[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)
