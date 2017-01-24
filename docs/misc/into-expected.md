---
title: "Требуется Into. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36615"
  - "vbc36615"
helpviewer_keywords: 
  - "BC36615"
ms.assetid: 24062dd9-a973-43b6-88d3-c11adc5a3736
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Требуется Into.
Предложение `Aggregate`, `Group By` или `Group Join` было указано без оператора `Into`. Оператор `Into` используется для идентификации агрегатных функций, которые должны применяться к результатам запроса, и для определения члена типа результата запроса, который должен содержать сгруппированные результаты \(с помощью агрегатной функции `Group`\).  
  
 **Идентификатор ошибки:** BC36615  
  
### Исправление ошибки  
  
1.  Добавьте оператор `Into` в предложение `Aggregate`, `Group By` или `Group Join`. Ниже представлен пример такого кода.  
  
    ```vb#  
    Dim orders = From order In orderList _ Order By order.OrderDate _ Group By OrderDate = order.OrderDate _ Into OrdersByDate = Group  
    ```  
  
## См. также  
 [Предложение Aggregate](../Topic/Aggregate%20Clause%20\(Visual%20Basic\).md)   
 [Предложение Group By](../Topic/Group%20By%20Clause%20\(Visual%20Basic\).md)   
 [Предложение Group Join](../Topic/Group%20Join%20Clause%20\(Visual%20Basic\).md)   
 [Знакомство с LINQ в Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)