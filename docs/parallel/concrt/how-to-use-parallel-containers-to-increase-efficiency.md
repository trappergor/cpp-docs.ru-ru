---
title: Практическое руководство. Использование параллельных контейнеров для повышения эффективности
ms.date: 11/04/2016
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
ms.openlocfilehash: 361e0e32efb45468ba108ee975879f990ac98395
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008327"
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>Практическое руководство. Использование параллельных контейнеров для повышения эффективности

В этом разделе показано, как использовать параллельные контейнеры для эффективного хранения и доступа к данным в параллельном режиме.

В примере кода выполняется параллельное вычисление набора простых и Кармичаел чисел. Затем для каждого числа Кармичаел код вычислит простые коэффициенты этого числа.

## <a name="example-determine-if-an-input-value-is-a-prime-number"></a>Пример. определение, является ли входное значение простым числом

В следующем примере показана `is_prime` функция, которая определяет, является ли входное значение простым числом, и `is_carmichael` функцию, которая определяет, является ли входное значение кармичаел числом.

[!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]

## <a name="example-compute-prime-and-carmichael-numbers"></a>Пример: вычисление простых и Кармичаел чисел

В следующем примере используются `is_prime` функции и `is_carmichael` для расчета наборов простых и кармичаел чисел. В примере используются алгоритмы [параллелизма::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) и [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) для параллельного расчета каждого набора. Дополнительные сведения о параллельных алгоритмах см. в разделе [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

В этом примере используется объект [Concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) для хранения набора чисел кармичаел, так как он впоследствии будет использовать этот объект в качестве рабочей очереди. Он использует объект [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) для хранения набора простых чисел, так как впоследствии он будет выполнять итерацию по этому набору для поиска простых факторов.

[!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]

## <a name="example-find-all-prime-factors-of-a-given-value"></a>Пример. Поиск всех простых факторов заданного значения

В следующем примере показана `prime_factors_of` функция, которая использует пробное деление для поиска всех простых факторов заданного значения.

Эта функция использует алгоритм [arallel_for_each Concurrency::p](reference/concurrency-namespace-functions.md#parallel_for_each) для прохода по коллекции простых чисел. `concurrent_vector`Объект позволяет параллельному циклу одновременно добавлять в результат простые факторы.

[!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]

## <a name="example-processes-each-element-in-the-queue-of-carmichael-numbers"></a>Пример. обрабатывает каждый элемент в очереди номеров Кармичаел

В этом примере каждый элемент в очереди чисел Кармичаел обрабатывается путем вызова `prime_factors_of` функции для расчета своих простых факторов. Она использует группу задач для параллельного выполнения этой операции. Дополнительные сведения о группах задач см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

В этом примере выводятся простые факторы для каждого Кармичаел числа, если это число имеет более четырех простых факторов.

[!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]

## <a name="example-finished-parallel-container-code-sample"></a>Пример. завершенный пример параллельного кода контейнера

В следующем коде показан полный пример, в котором используются параллельные контейнеры для расчета простых факторов чисел Кармичаел.

[!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]

В этом примере выводится следующий пример выходных данных.

```Output
Prime factors of 9890881 are: 7 11 13 41 241.
Prime factors of 825265 are: 5 7 17 19 73.
Prime factors of 1050985 are: 5 13 19 23 37.
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем, `carmichael-primes.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc кармичаел-примес. cpp**

## <a name="see-also"></a>См. также статью

[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Параллельное выполнение задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Класс concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)<br/>
[Класс concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)<br/>
[Функция parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)<br/>
[Функция parallel_for](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[Класс task_group](reference/task-group-class.md)
