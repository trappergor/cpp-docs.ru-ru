---
title: 'Как: использование класса combinable для повышения производительности | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3185ee9f7546e6927197d2e3452ea4cf86f9ab5c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-combinable-to-improve-performance"></a>Практическое руководство. Использование класса combinable для повышения производительности
В этом примере показано, как использовать [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класса для вычисления суммы чисел в [std::array](../../standard-library/array-class-stl.md) объекта, которые являются простыми. `combinable` Класс повысить производительность, устраняя общее состояние.  
  
> [!TIP]
>  В некоторых случаях параллельное сопоставление ([concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) и уменьшения ([параллелизма:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)) может дать выигрыш в производительности по `combinable`. Пример сопоставления использует, а также уменьшить объем операций, чтобы получить те же результаты, как в этом примере, в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется [std::accumulate](../../standard-library/numeric-functions.md#accumulate) функции для вычисления суммы элементов массива, которые являются простыми числами. В этом примере `a` — `array` объекта и `is_prime` функция определяет, является ли входное значение простым.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]  
  
## <a name="example"></a>Пример  

 В следующем примере показано упрощенный способ параллельного выполнения предыдущего примера. В этом примере используется [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм для обработки массиве в параллельном режиме и [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) объект для синхронизации доступа к `prime_sum` переменной . В этом примере не масштабируется, так как каждый поток должен ждать общий ресурс станет доступным.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `combinable` объекта для повышения производительности в предыдущем примере. В этом примере устраняет необходимость в объектах синхронизации; он является масштабируемым, так как `combinable` объекта позволяет каждому потоку выполнять свою задачу независимо друг от друга.  
  
 Объект `combinable` обычно используется в два этапа. Во-первых для создания последовательности детализированные вычисления, выполняя работу в параллельном режиме. Затем объединения (или уменьшить) вычислений в конечный результат. В этом примере используется [concurrency::combinable::local](reference/combinable-class.md#local) метод для получения ссылки на локальную сумму. Затем он использует [Concurrency::combinable::](reference/combinable-class.md#combine) метод и [std::plus](../../standard-library/plus-struct.md) объекта для объединения локальных вычислений в конечный результат.  

  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]  
  
## <a name="example"></a>Пример  
 Следующий пример вычисляет сумму оба простых чисел последовательно и параллельно. Пример выводит на консоль время, необходимое на выполнение обоих вычислений.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]  
  
 В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.  
  
```Output  
1709600813  
serial time: 6178 ms  
 
1709600813  
parallel time: 1638 ms  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `parallel-sum-of-primes.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc параллельного sum-of-primes.cpp**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Пример сопоставления использует, а также уменьшить объем операций можно получить те же результаты, в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="see-also"></a>См. также  
 [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)   
 [Класс combinable](../../parallel/concrt/reference/combinable-class.md)   
 [Класс critical_section](../../parallel/concrt/reference/critical-section-class.md)
