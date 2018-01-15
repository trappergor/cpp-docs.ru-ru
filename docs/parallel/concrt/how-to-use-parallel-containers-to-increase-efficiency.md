---
title: "Как: использование параллельных контейнеров для повышения эффективности | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64b191b97bcf4b5f1607cde56fac8fefd1505c7c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>Практическое руководство. Использование параллельных контейнеров для повышения эффективности
В этом разделе демонстрируется использование параллельных контейнеров для эффективного хранения и доступа к данным в параллельном режиме.  
  
 Пример кода вычисляет набор простых чисел и чисел Кармайкла параллельно. Затем для каждого числа Кармайкла вычисляются простые множители этого числа.  
  
## <a name="example"></a>Пример  
 В следующем примере показан `is_prime` функции, которая определяет, является ли входное значение простых чисел, а `is_carmichael` функции, которая определяет, является ли входное значение числа Кармайкла.  
  
 [!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `is_prime` и `is_carmichael` функции для вычисления наборов простых чисел и чисел Кармайкла. В этом примере [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) и [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритмы для вычисления каждый набор в параллельном режиме. Дополнительные сведения о параллельных алгоритмах см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).  
  
 В этом примере используется [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) объекта, содержащего набор Кармайкла порядковые номера, так как он будет использоваться этот объект как рабочей очереди. Она использует [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) объекта, содержащего набор простых чисел, так как он будет позже итерации исходный набор, чтобы найти простые множители.  
  
 [!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере показан `prime_factors_of` функции, которая для поиска всех простых множителей заданного значения используется пробное деление.  
  
 Эта функция использует [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм для прохода по коллекции простых чисел. `concurrent_vector` Позволяет параллельного цикла одновременно добавлять простые множители к результату.  
  
 [!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]  
  
## <a name="example"></a>Пример  
 В данном примере каждый элемент в очереди чисел Кармайкла обрабатывается путем вызова `prime_factors_of` для вычисления простых множителей. Для параллельного выполнения этой работы используется группа задач. Дополнительные сведения о группах задач см. в разделе [параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 В этом примере вывод простых множителей для каждого числа Кармайкла, если это число имеет более четырех простых множителей.  
  
 [!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]  
  
## <a name="example"></a>Пример  
 Ниже приведен полный пример, в котором используются параллельные контейнеры для вычисления простых множителей чисел Кармайкла.  
  
 [!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]  
  
 В этом примере получается следующий результат.  
  
```Output  
Prime factors of 9890881 are: 7 11 13 41 241.  
Prime factors of 825265 are: 5 7 17 19 73.  
Prime factors of 1050985 are: 5 13 19 23 37.  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `carmichael-primes.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc Кармайкла primes.cpp**  
  
## <a name="see-also"></a>См. также  
 [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)   
 [Параллелизм задач](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Класс concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)   
 [Класс concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)   
 [Функция parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)   
 [Функция parallel_for](reference/concurrency-namespace-functions.md#parallel_for)   
 [Класс task_group](reference/task-group-class.md)
