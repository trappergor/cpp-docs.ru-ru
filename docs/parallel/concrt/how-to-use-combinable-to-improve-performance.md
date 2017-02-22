---
title: "Практическое руководство. Использование класса combinable для повышения производительности | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс combinable, пример"
  - "повышение параллельной производительности с помощью класса combinable [среда выполнения с параллелизмом]"
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Практическое руководство. Использование класса combinable для повышения производительности
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом примере показано, как использовать класс [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md), чтобы вычислять сумму простых чисел в объекте [std::array](../../standard-library/array-class-stl.md).  Класс `combinable` повышает производительность за счет исключения совместно используемого состояния.  
  
> [!TIP]
>  В некоторых случаях параллельное сопоставление \([concurrency::parallel\_transform](../Topic/parallel_transform%20Function.md)\) и снижение \([concurrency:: parallel\_reduce](../Topic/parallel_reduce%20Function.md)\) может предоставлять увеличение производительности по сравнению с `combinable`.  Пример, использующий операции сопоставления и снижения для получения тех же результатов, что и в этом примере, см. в разделе [Параллельные алгоритмы](../Topic/Parallel%20Algorithms.md).  
  
## Пример  
 В следующем примере функция [std::accumulate](../Topic/accumulate.md) используется для вычисления суммы элементов массива, которые являются простыми числами.  В этом примере `a` является объектом `array`, а функция `is_prime` определяет, является ли входное значение простым числом.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_1.cpp)]  
  
## Пример  
 В следующем примере демонстрируется наивный способ параллельного выполнения предыдущего примера.  В этом примере алгоритм [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) используется для параллельной обработки массива, а объект [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) используется для синхронизации доступа к переменной `prime_sum`.  Этот пример не является масштабируемым, так как каждый поток должен ожидать, пока станет доступным совместно используемый ресурс.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_2.cpp)]  
  
## Пример  
 В следующем примере объект `combinable` используется повышения производительности предыдущего примера.  В этом примере исключается необходимость в объектах синхронизации; он является масштабируемым, так как объект `combinable` позволяет каждому потоку выполнять свою задачу независимо.  
  
 Объект `combinable` обычно используется в два этапа.  Сначала для создания последовательности мелких фрагментов вычислений для параллельной обработки.  Затем для объединения \(или сокращения\) вычислений в конечный результат.  В этом примере для получения ссылки на локальную сумму используется метод [concurrency::combinable::local](../Topic/combinable::local%20Method.md).  Затем используются метод [concurrency::combinable::combine](../Topic/combinable::combine%20Method.md) и объект [std::plus](../../standard-library/plus-struct.md), чтобы объединить вычисления в конечный результат.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_3.cpp)]  
  
## Пример  
 В следующем полном примере сумма простых чисел вычисляется как последовательно, так и параллельно.  В этом примере на консоль выводится продолжительность выполнения этих двух вычислений.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/CPP/how-to-use-combinable-to-improve-performance_4.cpp)]  
  
 В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.  
  
  **1709600813**  
**последовательное время: 6178 мс**  
**1709600813**  
**параллельное время: 1638 мс**   
## Компиляция кода  
 Чтобы скомпилировать код, скопируйте и вставьте его в проект Visual Studio или в файл с именем `parallel-sum-of-primes.cpp`, затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe \/EHsc parallel\-sum\-of\-primes.cpp**  
  
## Отказоустойчивость  
 Пример, использующий операции сопоставление и снижения, чтобы получить те же результаты, см. в разделе [Параллельные алгоритмы](../Topic/Parallel%20Algorithms.md).  
  
## См. также  
 [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)   
 [Класс combinable](../../parallel/concrt/reference/combinable-class.md)   
 [Класс critical\_section](../../parallel/concrt/reference/critical-section-class.md)