---
title: "Методы доступа к свойствам нельзя объявить как &quot;&lt;ключевое слово&gt;&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31099"
  - "bc31099"
helpviewer_keywords: 
  - "BC31099"
ms.assetid: d6f3b989-39b9-4c47-995a-bd83ec03d7b8
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Методы доступа к свойствам нельзя объявить как &quot;&lt;ключевое слово&gt;&quot;
Объявление процедуры `Get` или `Set` содержит ключевое слово, которое является недопустимым для процедур свойств.  
  
 [Оператор Get](../Topic/Get%20Statement.md) и [Оператор Set](../Topic/Set%20Statement%20\(Visual%20Basic\).md) допускают только модификатор доступа \(`Public`, `Protected`, `Friend`, `Protected Friend`, `Private`\).  
  
 **Идентификатор ошибки:** BC31099  
  
### Исправление ошибки  
  
-   Удалите недопустимое ключевое слово из оператора `Get` или `Set`.  
  
## См. также  
 [Процедуры свойств](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)   
 [Практическое руководство. Объявление свойства со смешанным уровнем доступа](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)