---
title: 'Как: выполнять карты и уменьшить объем операций параллельно | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cda761da013e966f91848fed01a4f96f5d373021
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>Практическое руководство. Параллельное выполнение операций сопоставления и сокращения числа элементов

В этом примере показано, как использовать [concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) и [concurrency::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) алгоритмы и [concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)для подсчета вхождений слов в файлах.  
  
 Объект *карты* применяет функцию к каждому значению в последовательности. Объект *уменьшить* объединяет элементы последовательности в одно значение. Можно использовать стандартную библиотеку C++ [std::transform](../../standard-library/algorithm-functions.md#transform) и [std::accumulate](../../standard-library/numeric-functions.md#accumulate) функции для выполнения сопоставления и уменьшить объем операций. Однако для повышения производительности при многих проблемах можно использовать алгоритм `parallel_transform` для параллельного выполнения операции сопоставления и алгоритм `parallel_reduce` для параллельного выполнения операции редукции. В некоторых случаях можно использовать `concurrent_unordered_map` для выполнения сопоставления и операции редукции в одной операции.  
  
## <a name="example"></a>Пример  
 В следующем примере подсчитываются вхождения слов в файлах. Она использует [std::vector](../../standard-library/vector-class.md) для представления содержимого двух файлов. Операция сопоставления подсчитывает вхождения каждого слова в каждом векторе. Операция редукции накапливает подсчет слов в обоих векторах.  
  
 [!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его и затем вставьте его в проект Visual Studio или в файл с именем `parallel-map-reduce.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc parallel-Word-MINING.cpp**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 В этом примере можно использовать класс `concurrent_unordered_map`, который определен в concurrent_unordered_map.h, чтобы выполнять сопоставление и редукцию в одной операции.  
  
 [!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]  
  
 Как правило, вы параллелизуете только внешний или внутренний цикл. Параллелизуйте внутренний цикл при наличии относительно небольшого числа файлов, когда каждый файл содержит много слов. Параллелизуйте внешний цикл при наличии довольно большого числа файлов, когда каждый файл содержит мало слов.  
  
## <a name="see-also"></a>См. также  
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)   
 [Функция parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)   
 [Функция parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)   
 [Класс concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
