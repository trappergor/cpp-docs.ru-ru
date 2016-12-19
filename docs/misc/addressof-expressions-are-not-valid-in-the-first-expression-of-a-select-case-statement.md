---
title: "Выражения AddressOf являются недопустимыми в первом выражении инструкции Select Case. | Microsoft Docs"
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
  - "bc36636"
  - "vbc36636"
helpviewer_keywords: 
  - "BC36636"
ms.assetid: 2ccc0ccc-d4d0-4910-8859-dedfa57c8126
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Выражения AddressOf являются недопустимыми в первом выражении инструкции Select Case.
Нельзя использовать выражение `AddressOf` для выражения проверки в операторе `Select Case`. Выражения `AddressOf` возвращают делегаты функций, и выражение проверки в операторе `Select Case` должно иметь простой тип данных.  
  
 **Идентификатор ошибки:** BC36636  
  
### Исправление ошибки  
  
-   Проверьте свой код, чтобы определить, подойдет ли вам другая условная конструкция, например оператор `If...Then...Else`.  
  
## См. также  
 [Оператор AddressOf](../Topic/AddressOf%20Operator%20\(Visual%20Basic\).md)   
 [Оператор If...Then...Else](../Topic/If...Then...Else%20Statement%20\(Visual%20Basic\).md)   
 [Оператор Select...Case](../Topic/Select...Case%20Statement%20\(Visual%20Basic\).md)