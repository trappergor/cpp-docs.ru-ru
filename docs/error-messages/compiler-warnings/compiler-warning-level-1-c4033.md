---
title: "Предупреждение компилятора (уровень&#160;1) C4033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4033"
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень&#160;1) C4033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Функция "функция" должна возвращать значение  
  
 Функция не возвращает значение. Возвращается неопределенное значение.  
  
 Функции, использующие `return` без возвращаемого значения, должны объявляться с типом `void`.  
  
 Эта ошибка для кода на языке C.  
  
 Следующий пример приводит к возникновению ошибки C4033:  
  
```  
// C4033.c // compile with: /W1 /LD int test_1(int x)   // C4033 expected { if (x) { return;   // C4033 } }  
```