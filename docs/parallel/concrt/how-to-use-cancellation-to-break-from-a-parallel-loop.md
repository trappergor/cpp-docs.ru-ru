---
title: "Практическое руководство. Использование отмены для выхода из параллельного цикла | Microsoft Docs"
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
  - "алгоритм параллельного поиска, создание [среда выполнения с параллелизмом]"
  - "создание алгоритма параллельного поиска [среда выполнения с параллелизмом]"
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
caps.latest.revision: 19
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Использование отмены для выхода из параллельного цикла
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом примере показано, как использовать отмену для реализации простого алгоритма параллельного поиска.  
  
## Пример  
 В следующем примере отмена используется для поиска элемента в массиве.  Функция `parallel_find_any` использует алгоритм [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) и функцию [concurrency::run\_with\_cancellation\_token](../Topic/run_with_cancellation_token%20Function.md) для поиска позиции, содержащей данное значение.  Если параллельный цикл находит значение, он вызывает метод [concurrency::cancellation\_token\_source::cancel](../Topic/cancellation_token_source::cancel%20Method.md) для отмены дальнейшей работы.  
  
 [!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/CPP/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]  
  
 Алгоритм [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) работает параллельно.  Поэтому он не выполняет операции в заранее заданном порядке.  Если массив содержит несколько вхождений требуемого значения, результатом может быть любая из таких позиций.  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `parallel-array-search.cpp`, затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe \/EHsc parallel\-array\-search.cpp**  
  
## См. также  
 [Отмена](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Параллельные алгоритмы](../Topic/Parallel%20Algorithms.md)   
 [Функция parallel\_for](../Topic/parallel_for%20Function.md)   
 [Класс cancellation\_token\_source](../../parallel/concrt/reference/cancellation-token-source-class.md)