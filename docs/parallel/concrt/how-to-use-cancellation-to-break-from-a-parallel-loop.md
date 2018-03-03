---
title: "Как: использование отмены для выхода из параллельного цикла | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27c6b4a216609c788978e4b857b5996587f899f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>Практическое руководство. Использование отмены для выхода из параллельного цикла
В этом примере показано, как использовать отмену для реализации простого алгоритма параллельного поиска.  
  
## <a name="example"></a>Пример  

 В следующем примере отмены для поиска элемента в массиве. `parallel_find_any` Функция использует [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм и [concurrency::run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) для поиска позиции, содержащей данное значение. Если параллельный цикл находит это значение, он вызывает [Concurrency::cancellation_token_source:: Cancel](reference/cancellation-token-source-class.md#cancel) метода для отмены дальнейшей работы.  


  
 [!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]  
  

 [Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм работает параллельно. Таким образом он не выполняет операции в предварительно определенном порядке. Если массив содержит несколько экземпляров значения, результат может быть любым из его позиции.  

  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `parallel-array-search.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **/ EHsc CL.exe parallel-array-search.cpp**  
  
## <a name="see-also"></a>См. также  
 [Отмена в библиотеке параллельных Шаблонов](cancellation-in-the-ppl.md)   
 [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md)   
 [Функция parallel_for](reference/concurrency-namespace-functions.md#parallel_for)   
 [Класс cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)
