---
title: "New не может использоваться в интерфейсе. | Microsoft Docs"
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
  - "vbc30375"
  - "bc30375"
helpviewer_keywords: 
  - "BC30375"
ms.assetid: c1e06108-1b52-4cbe-8cae-e816a0dbac0b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# New не может использоваться в интерфейсе.
Инструкция [Оператор Dim](../Topic/Dim%20Statement%20\(Visual%20Basic\).md) использует предложение [Оператор New](../Topic/New%20Operator%20\(Visual%20Basic\).md) при объявлении переменной с типом интерфейса.  
  
 Хотя интерфейс является ссылочным типом, вы не можете создавать его экземпляр. Можно использовать `New` только для создания экземпляра класса или структуры.  
  
 **Идентификатор ошибки:** BC30375  
  
### Исправление ошибки  
  
1.  Если переменная должна иметь тип интерфейса, удалите ключевое слово `New`.  
  
2.  Если переменная существует для ссылки на экземпляр, объявите ее с типом класса или структуры. Оставьте ключевое слово `New` для создания экземпляра.  
  
## См. также  
 [Оператор Interface](../Topic/Interface%20Statement%20\(Visual%20Basic\).md)   
 [Оператор Class](../Topic/Class%20Statement%20\(Visual%20Basic\).md)   
 [Оператор Structure](../Topic/Structure%20Statement.md)