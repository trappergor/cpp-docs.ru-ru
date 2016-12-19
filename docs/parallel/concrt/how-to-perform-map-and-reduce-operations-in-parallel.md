---
title: "Практическое руководство. Параллельное выполнение операций сопоставления и сокращения числа элементов | Microsoft Docs"
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
  - "функция parallel_transform, пример"
  - "параллельное сопоставление и уменьшение, пример"
  - "функция parallel_reduce, пример"
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Параллельное выполнение операций сопоставления и сокращения числа элементов
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом примере показано, как использовать [concurrency::parallel_transform](../Topic/parallel_transform%20Function.md) и [concurrency::parallel_reduce](../Topic/parallel_reduce%20Function.md) алгоритмы и [concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) класса для подсчета вхождений слова в файлах.  
  
 A *карты* применяет функцию к каждому значению в последовательности. A *уменьшить* объединяет элементы последовательности в одно значение. Можно использовать библиотеки стандартных шаблонов (STL) [std::transform](../Topic/transform.md)[std::accumulate](../Topic/accumulate.md) классы для выполнения сопоставления и уменьшить объем операций. Однако для повышения производительности при многих проблемах можно использовать алгоритм `parallel_transform` для параллельного выполнения операции сопоставления и алгоритм `parallel_reduce` для параллельного выполнения операции редукции. В некоторых случаях можно использовать `concurrent_unordered_map` для выполнения сопоставления и операции редукции в одной операции.  
  
## <a name="example"></a>Пример  
 В следующем примере подсчитываются вхождения слов в файлах. Он использует [std::vector](vector%20Class.md) для представления содержимого двух файлов. Операция сопоставления подсчитывает вхождения каждого слова в каждом векторе. Операция редукции накапливает подсчет слов в обоих векторах.  
  
 [!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/CPP/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `parallel-map-reduce.cpp` и затем выполните следующую команду в окне командной строки Visual Studio.  
  
 **/ EHsc CL.exe параллельного map-reduce.cpp**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 В этом примере можно использовать класс `concurrent_unordered_map`, который определен в concurrent_unordered_map.h, чтобы выполнять сопоставление и редукцию в одной операции.  
  
 [!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/CPP/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]  
  
 Как правило, вы параллелизуете только внешний или внутренний цикл. Параллелизуйте внутренний цикл при наличии относительно небольшого числа файлов, когда каждый файл содержит много слов. Параллелизуйте внешний цикл при наличии довольно большого числа файлов, когда каждый файл содержит мало слов.  
  
## <a name="see-also"></a>См. также  
 [Параллельные алгоритмы](../Topic/Parallel%20Algorithms.md)   
 [Функция parallel_transform](../Topic/parallel_transform%20Function.md)   
 [Функция parallel_reduce](../Topic/parallel_reduce%20Function.md)   
 [Класс concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
