---
title: "Option Strict On запрещает неявное преобразование из &quot;&lt;тип1&gt;&quot; в &quot;&lt;тип2&gt;&quot;; коллекции Visual Basic&#160;6.0 несовместимы как тип с коллекциями .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30753"
  - "bc30753"
helpviewer_keywords: 
  - "BC30753"
ms.assetid: 7e1bb22e-a507-483e-bfd6-f3a43e24a232
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On запрещает неявное преобразование из &quot;&lt;тип1&gt;&quot; в &quot;&lt;тип2&gt;&quot;; коллекции Visual Basic&#160;6.0 несовместимы как тип с коллекциями .NET Framework
`Option Strict On` запрещает неявные преобразования из "`<type1>`" в "`<type2>`"; тип коллекций Visual Basic 6.0 несовместим с типом коллекций [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)].  
  
 Объект коллекции, используемый в Visual Basic 6.0, отличается от объекта коллекции, используемого в [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)].  
  
 **Идентификатор ошибки:** BC30753  
  
### Исправление ошибки  
  
-   Явно преобразовывайте объекты коллекций с помощью одного из ключевых слов преобразования типов. Ключевые слова [Функция CType](../Topic/CType%20Function%20\(Visual%20Basic\).md) и [Оператор DirectCast](../Topic/DirectCast%20Operator%20\(Visual%20Basic\).md) вызывают исключение времени выполнения, если происходит сбой преобразования. Ключевое слово [Оператор TryCast](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md) возвращает [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md) при сбое преобразования.  
  
## См. также  
 [Функция CType](../Topic/CType%20Function%20\(Visual%20Basic\).md)   
 [Оператор DirectCast](../Topic/DirectCast%20Operator%20\(Visual%20Basic\).md)   
 [Оператор TryCast](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md)   
 [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md)   
 [NIB Коллекции в Visual Basic](http://msdn.microsoft.com/ru-ru/8b2b7845-2251-4573-8dd3-c9f9c0a66a21)