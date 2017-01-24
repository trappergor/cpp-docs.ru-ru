---
title: "Оператор &quot;&lt;оператор&gt;&quot; должен иметь тип возврата Boolean | Microsoft Docs"
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
  - "vbc33023"
  - "bc33023"
helpviewer_keywords: 
  - "BC33023"
ms.assetid: 18e066f4-d71e-4e38-b0bc-8af9145f6015
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор &quot;&lt;оператор&gt;&quot; должен иметь тип возврата Boolean
Оператор сравнения или логический оператор объявлен с типом возврата, отличным от [Тип данных Boolean](../Topic/Boolean%20Data%20Type%20\(Visual%20Basic\).md).  
  
 Результатом выполнения оператора сравнения \(`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `IsFalse`, `IsTrue`, `Like`, `TypeOf`\) может быть только значение `True` или `False`. Для получения дополнительной информации см. [Операторы сравнения в Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md).  
  
 Логические операторы \(`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`\) работают целиком в пределах домена логических значений. Для получения дополнительной информации см. [Логические и побитовые операторы в Visual Basic](../Topic/Logical%20and%20Bitwise%20Operators%20in%20Visual%20Basic.md).  
  
 **Идентификатор ошибки:** BC33023  
  
### Исправление ошибки  
  
-   Замените тип возврата этого оператора сравнения или логического оператора на `Boolean`.  
  
## См. также  
 [Процедуры операторов](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Оператор Operator](../Topic/Operator%20Statement.md)   
 [Практическое руководство. Определение оператора](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [Практическое руководство. Определение оператора преобразования](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)