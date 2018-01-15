---
title: "Как: преобразование параллельного цикла использовать среду выполнения с параллелизмом OpenMP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a27e07884b4ada54f694136ea2fbca474c9d214d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>Практическое руководство. Преобразование параллельного цикла for OpenMP для использования среды выполнения с параллелизмом

В этом примере показано, как преобразовать простой цикл, использующий OpenMP [параллельных](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) и [для](../../parallel/openmp/reference/for-openmp.md) директивы для использования среды выполнения с параллелизмом [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм.  
  
## <a name="example"></a>Пример  
 В этом примере используется как OpenMP, так и среда выполнения с параллелизмом для вычисления количества простых чисел в массиве случайных значений.  
  
 [!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]  
  
 В этом примере формируются следующие данные:  
  
```Output  
Using OpenMP...  
found 107254 prime numbers.  
Using the Concurrency Runtime...  
found 107254 prime numbers.  
```  
  
 `parallel_for` Алгоритм и OpenMP 3.0 позволяют тип индекса быть целочисленным типом со знаком или без знака целочисленный тип. `parallel_for` Алгоритм также гарантирует, что указанный диапазон не переполнений тип со знаком. OpenMP версий 2.0 и 2.5 позволяют знаком только целочисленные типы индекса. OpenMP также не проверяет диапазон индекса.  
  
 Версия этого примера, который использует среду выполнения с параллелизмом также использует [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) объекта вместо [atomic](../../parallel/openmp/reference/atomic.md) директивы для увеличения значения счетчика без необходимости синхронизация.  
  
 Дополнительные сведения о `parallel_for` и других параллельных алгоритмах см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md). Дополнительные сведения о `combinable` см. в описании [параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="example"></a>Пример  

 В этом примере изменяется предыдущий действовать от [std::array](../../standard-library/array-class-stl.md) объекта вместо на собственный массив. Так как OpenMP версий 2.0 и 2.5 разрешается только в со знаком целочисленные типы индекса `parallel_for` конструкции, итераторы нельзя использовать для доступа к элементам контейнера стандартной библиотеки C++ в параллельном режиме. Библиотека параллельных шаблонов (PPL) предоставляет [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм, который выполняет задачи, в параллельном режиме, в итеративном контейнере, например предоставленных библиотекой стандартной библиотеки C++. Он использует ту же логику секционирования, `parallel_for` алгоритмом. `parallel_for_each` Стандартной библиотеки C++ напоминает алгоритм [std::for_each](../../standard-library/algorithm-functions.md#for_each) алгоритм, за исключением того, что `parallel_for_each` алгоритм выполняет задачи параллельно.  
  
 [!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `concrt-omp-count-primes.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc/OpenMP concrt-omp-count-primes.cpp**  
  
## <a name="see-also"></a>См. также  
 [Переход от OpenMP к среде выполнения с параллелизмом](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)   
 [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)

