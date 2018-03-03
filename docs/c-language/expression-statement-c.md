---
title: "Оператор-выражение в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75bad42ddff5f20d14d627e3f036659f030bb3f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expression-statement-c"></a>Оператор выражений (C)
Когда выполняется оператор-выражение, соответствующее выражение оценивается по правилам, описанным в статье [Выражения и присваивания](../c-language/expressions-and-assignments.md).  
  
## <a name="syntax"></a>Синтаксис  
 *expression-statement*:  
 *expression* opt**;**  
  
 Все побочные эффекты от вычисления выражений выполняются до перехода к следующему оператору. Пустой оператор выражения называется неопределенным оператором. Дополнительные сведения см. в статье [Оператор NULL (C)](../c-language/null-statement-c.md).  
  
 В следующих примерах демонстрируются операторы выражения.  
  
```  
x = ( y + 3 );            /* x is assigned the value of y + 3  */  
x++;                      /* x is incremented                  */  
x = y = 0;                /* Both x and y are initialized to 0 */  
proc( arg1, arg2 );       /* Function call returning void      */  
y = z = ( f( x ) + 3 );   /* A function-call expression        */  
```  
  
 В последней строке приводится пример выражения вызова функции. Значение этого выражения (т. е. значение, возвращаемое функцией) увеличивается на 3, а затем присваивается обеим переменным: `y` и `z`.  
  
## <a name="see-also"></a>См. также  
 [Операторы](../c-language/statements-c.md)