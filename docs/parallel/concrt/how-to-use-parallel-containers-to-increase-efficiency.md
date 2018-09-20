---
title: 'Практическое: использование параллельных контейнеров для повышения эффективности | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71a4aee5664864b5a9c803ac5048e8e5b5eacf0a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383315"
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>Практическое руководство. Использование параллельных контейнеров для повышения эффективности

В этом разделе показано, как использование параллельных контейнеров для эффективного хранения и доступа к данным в параллельном режиме.

В примере кода вычисляет набор простых чисел и чисел Кармайкла в параллельном режиме. Затем для каждого числа Кармайкла код вычисляет простых множителей этого числа.

## <a name="example"></a>Пример

В следующем примере показан `is_prime` функцию, которая определяет, является ли входное значение простое число, и `is_carmichael` функцию, которая определяет, является ли входное значение числа Кармайкла.

[!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]

## <a name="example"></a>Пример

В следующем примере используется `is_prime` и `is_carmichael` функции для вычисления наборов простых чисел и чисел Кармайкла. В примере используется [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) и [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритмы для вычисления каждой наборе в параллельном режиме. Дополнительные сведения об алгоритмах параллельных операций, см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

В этом примере используется [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) объекта, содержащего набор Кармайкла номера, так как он будет использоваться этот объект как рабочей очереди. Она использует [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) объекта, содержащего набор простых чисел, так как она будет позже перебора этого набора для поиска простых множителей.

[!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]

## <a name="example"></a>Пример

В следующем примере показан `prime_factors_of` функцию, которая используется для поиска всех простых множителей заданного значения пробное деление.

Эта функция использует [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм для прохода по коллекции простых чисел. `concurrent_vector` Объект обеспечивает параллельного цикла одновременно добавлять простых множителей к результату.

[!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]

## <a name="example"></a>Пример

Этот пример обрабатывает каждый элемент в очереди чисел Кармайкла путем вызова `prime_factors_of` функции для вычисления простых множителей. Он использует группу задач для выполнения этой работы в параллельном режиме. Дополнительные сведения о группах задач см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Этот пример выводит простых множителей для каждого числа Кармайкла, если это число имеет более четырех простых множителей.

[!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]

## <a name="example"></a>Пример

Ниже приведен полный пример, в котором для вычисления простых множителей чисел Кармайкла используются параллельные контейнеры.

[!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]

В этом примере получается следующий результат.

```Output
Prime factors of 9890881 are: 7 11 13 41 241.
Prime factors of 825265 are: 5 7 17 19 73.
Prime factors of 1050985 are: 5 13 19 23 37.
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `carmichael-primes.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe Кармайкла primes.cpp**

## <a name="see-also"></a>См. также

[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Класс concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)<br/>
[Класс concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)<br/>
[Функция parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)<br/>
[Функция parallel_for](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[Класс task_group](reference/task-group-class.md)
