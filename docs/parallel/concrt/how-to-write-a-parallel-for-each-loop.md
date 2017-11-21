---
title: "Как: написание цикла parallel_for_each | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c3d641fe0437e371fdd45e2d497fbf865e41fa3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-write-a-parallelforeach-loop"></a>Практическое руководство. Написание цикла parallel_for_each
В этом примере показано, как использовать [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) алгоритм для вычисления количества простых чисел в [std::array](../../standard-library/array-class-stl.md) объекта в параллельном режиме.  
  
## <a name="example"></a>Пример  
 В следующем примере вычисляется количество простых чисел в массиве два раза. В примере сначала используется [std::for_each](../../standard-library/algorithm-functions.md#for_each) алгоритм для подсчета последовательно. Затем в примере используется `parallel_for_each` алгоритм для выполнения той же задачи параллельно. В этом примере в консоль также выводится время, необходимое на выполнение обоих вычислений.  
  
 [!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]  
  
 В следующем примере показаны выходные данные, полученные на четырехпроцессорном компьютере.  
  
```Output  
serial version:  
found 17984 prime numbers  
took 6115 ms  
 
parallel version:  
found 17984 prime numbers  
took 1653 ms  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `parallel-count-primes.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **/ EHsc CL.exe parallel-count-primes.cpp**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Лямбда-выражения, в примере передается `parallel_for_each` алгоритм использует `InterlockedIncrement` функцией для включения параллельных итераций цикла одновременно увеличивается счетчик. При использовании функции `InterlockedIncrement` для синхронизации доступа к общим ресурсам, можно представить узких мест в коде. Можно использовать механизм синхронизации без блокировки, например, [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класса, чтобы исключить одновременный доступ к общим ресурсам. Пример, использующий `combinable` таким образом см. в описании [как: использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).  
  
## <a name="see-also"></a>См. также  
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)   
 [Функция parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)


