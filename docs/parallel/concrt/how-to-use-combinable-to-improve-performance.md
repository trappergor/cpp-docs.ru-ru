---
title: Практическое руководство. Использование класса combinable для повышения производительности
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
ms.openlocfilehash: c8f4c40be84b2204e5b5632fe6d3d5a5d22b8719
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258129"
---
# <a name="how-to-use-combinable-to-improve-performance"></a>Практическое руководство. Использование класса combinable для повышения производительности

В этом примере показано, как использовать [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс для вычисления суммы значений в [std::array](../../standard-library/array-class-stl.md) объекта, которые являются простыми. `combinable` Класс повышает производительность, устраняя общее состояние.

> [!TIP]
>  В некоторых случаях параллельное сопоставление ([concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) и сокращения ([параллелизма:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)) обеспечивает повышение производительности, чем `combinable`. Например, использование операции сопоставления и редукции для создания те же результаты, что в этом примере, см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="example"></a>Пример

В следующем примере используется [std::accumulate](../../standard-library/numeric-functions.md#accumulate) функции для вычисления суммы элементов в массиве, которые являются простыми числами. В этом примере `a` — `array` объекта и `is_prime` функция определяет, является ли входное значение является простым.

[!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]

## <a name="example"></a>Пример

Следующий пример показывает упрощенный способ для параллельного выполнения предыдущего примера. В этом примере используется [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм для обработки массиве в параллельном режиме и [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) объект для синхронизации доступа к `prime_sum` переменной . В этом примере не масштабируется, так как каждый поток должен ждать по этому общему ресурсу, станут доступны.

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]

## <a name="example"></a>Пример

В следующем примере используется `combinable` объекта для повышения производительности в предыдущем примере. В этом примере избавляет от необходимости для объектов синхронизации. является масштабируемой, поскольку `combinable` объекта позволяет каждому потоку для выполнения задачи независимо друг от друга.

Объект `combinable` обычно используется в два этапа. Во-первых для создания последовательности детализированные вычисления, выполняя работу в параллельном режиме. Затем объединение (или уменьшить) вычислений в конечный результат. В этом примере используется [concurrency::combinable::local](reference/combinable-class.md#local) метод для получения ссылки на локальную сумму. Затем он использует [Concurrency::combinable:: Combine](reference/combinable-class.md#combine) метод и [std::plus](../../standard-library/plus-struct.md) объект для объединения локальных вычислений в конечный результат.

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]

## <a name="example"></a>Пример

Приведенный ниже полный пример вычисляет сумму оба простых чисел, последовательно и параллельно. В примере выводится на консоль время, необходимое на выполнение обоих вычислений.

[!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]

В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.

```Output
1709600813
serial time: 6178 ms

1709600813
parallel time: 1638 ms
```

## <a name="compiling-the-code"></a>Компиляция кода

Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или вставьте его в файл с именем `parallel-sum-of-primes.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**CL.exe/EHsc параллельного sum-of-primes.cpp**

## <a name="robust-programming"></a>Отказоустойчивость

Например, использование операции сопоставления и редукции для дают одинаковые результаты, см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="see-also"></a>См. также

[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Класс combinable](../../parallel/concrt/reference/combinable-class.md)<br/>
[Класс critical_section](../../parallel/concrt/reference/critical-section-class.md)
