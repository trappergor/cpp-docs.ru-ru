---
title: "Синтаксическая ошибка в операторе приведения типа; требуются два аргумента, разделенных запятой | Microsoft Docs"
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
  - "vbc30944"
  - "bc30944"
helpviewer_keywords: 
  - "BC30944"
ms.assetid: 1f7ed4a1-6ff5-4836-8424-21618c68ff45
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Синтаксическая ошибка в операторе приведения типа; требуются два аргумента, разделенных запятой
Выражение использует функцию преобразования `CType` или ключевое слово преобразования `DirectCast` или `TryCast`, но предоставляет только один аргумент.  
  
 `CType`, `DirectCast` и `TryCast` требуется по два аргумента. Первое — это выражение для преобразования, а второе — тип данных или тип класса, в который требуется его преобразовать.  
  
 **Идентификатор ошибки:** BC30944  
  
### Исправление ошибки  
  
-   Укажите оба аргумента, которые необходимы для преобразования.  
  
-   Если планируется использовать одну конкретную функцию [Функции преобразования типов](../Topic/Type%20Conversion%20Functions%20\(Visual%20Basic\).md), например `CString`, вы должны использовать это имя функции вместо `CType`. Тогда требуется только один аргумент.  
  
## См. также  
 [Функция CType](../Topic/CType%20Function%20\(Visual%20Basic\).md)   
 [Оператор DirectCast](../Topic/DirectCast%20Operator%20\(Visual%20Basic\).md)   
 [Оператор TryCast](../Topic/TryCast%20Operator%20\(Visual%20Basic\).md)   
 [Функции преобразования типов](../Topic/Type%20Conversion%20Functions%20\(Visual%20Basic\).md)