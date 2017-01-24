---
title: "Оператор выражений (C) | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "операторы выражений"
  - "операторы, выражение"
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор выражений (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Когда выполняется оператор выражения, соответствующее выражение вычисляется по правилам, приведенным в разделе [Выражения и присваивания](../c-language/expressions-and-assignments.md).  
  
## Синтаксис  
 *оператор\-выражения*:  
 *выражение*  необ **;**  
  
 Все побочные эффекты от вычисления выражений выполняются до перехода к следующему оператору.  Пустой оператор выражения называется неопределенным оператором.  Дополнительные сведения см. в разделе [Неопределенный оператор](../c-language/null-statement-c.md).  
  
 В следующих примерах демонстрируются операторы выражения.  
  
```  
x = ( y + 3 );            /* x is assigned the value of y + 3  */  
x++;                      /* x is incremented                  */  
x = y = 0;                /* Both x and y are initialized to 0 */  
proc( arg1, arg2 );       /* Function call returning void      */  
y = z = ( f( x ) + 3 );   /* A function-call expression        */  
```  
  
 В последней строке приводится пример выражения вызова функции. Значение этого выражения \(т. е. значение, возвращаемое функцией\) увеличивается на 3, а затем присваивается обеим переменным: `y` и `z`.  
  
## См. также  
 [Операторы](../c-language/statements-c.md)