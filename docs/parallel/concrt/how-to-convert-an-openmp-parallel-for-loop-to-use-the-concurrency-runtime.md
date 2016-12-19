---
title: "Практическое руководство. Преобразование параллельного цикла for OpenMP для использования среды выполнения с параллелизмом | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "преобразование OpenMP в среду выполнения с параллелизмом, параллельные циклы for"
  - "преобразование OpenMP в среду выполнения с параллелизмом, параллельные циклы"
  - "параллельные циклы for, преобразование OpenMP в среду выполнения с параллелизмом"
  - "параллельные циклы, преобразование OpenMP в среду выполнения с параллелизмом"
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
caps.latest.revision: 13
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Преобразование параллельного цикла for OpenMP для использования среды выполнения с параллелизмом
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом примере показано, как преобразовать простой цикл, использующий директивы [parallel](../../parallel/openmp/reference/parallel.md) и [for](../Topic/for%20\(OpenMP\).md) OpenMP, для использования алгоритма [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) среды выполнения с параллелизмом.  
  
## Пример  
 В этом примере для подсчета простых чисел в массиве произвольных значений используется как OpenMP, так и среда выполнения с параллелизмом.  
  
 [!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/CPP/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]  
  
 В результате выполнения примера получается следующий результат:  
  
  **Использование OpenMP…**  
**найденные простые числа 107254.**  
**использование среды выполнения с параллелизмом...**  
**найденные простые числа 107254.** Алгоритм `parallel_for` и OpenMP 3.0 допускают, чтобы тип индекса был целочисленным типом со знаком или без знака.  Алгоритм `parallel_for` также следит, чтобы указанный диапазон не переполнял тип со знаком.  OpenMP версий 2.0 и 2.5 допускает только целочисленные типы индекса со знаком.  OpenMP также не проверяет диапазон индекса.  
  
 Версия этого примера, использующая среду выполнения с параллелизмом, также использует объект [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) вместо директивы [atomic](../../parallel/openmp/reference/atomic.md), чтобы увеличивать значение счетчика без необходимости синхронизации.  
  
 Дополнительные сведения об алгоритме `parallel_for` и других параллельных алгоритмах см. в разделе [Параллельные алгоритмы](../Topic/Parallel%20Algorithms.md).  Дополнительные сведения о классе `combinable` см. в разделе [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Пример  
 Этот пример отличается от предыдущего тем, что работает с объектом [std::array](../../standard-library/array-class-stl.md), а не с собственным массивом.  Так как OpenMP версий 2.0 и 2.5 допускает целочисленные типы индекса со знаком только в конструкции `parallel` `for`, для параллельного доступа к элементам контейнера стандартной библиотеки шаблонов \(STL\) нельзя использовать итераторы.  Библиотека параллельных шаблонов \(PPL\) предоставляет алгоритм [Concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md), который параллельно выполняет задачи в итеративном контейнере, например предоставленные библиотекой STL.  В нем используется такая же логика секционирования, что и в алгоритме `parallel_for`.  Алгоритм `parallel_for_each` похож на алгоритм [std::for\_each](../Topic/for_each.md) из библиотеки STL, но алгоритм `parallel_for_each` выполняет задачи параллельно.  
  
 [!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/CPP/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект  или в файл с именем concrt\-omp\-count\-primes.cpp, затем выполните в окне командной строки следующую команду.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-count\-primes.cpp**  
  
## См. также  
 [Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Параллельные алгоритмы](../Topic/Parallel%20Algorithms.md)   
 [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)