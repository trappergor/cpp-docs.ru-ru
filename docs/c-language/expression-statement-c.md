---
title: Оператор выражений (C)
ms.date: 11/04/2016
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
ms.openlocfilehash: 736ed4fbbd9f87c675c0bb9566c6c31287e77917
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148794"
---
# <a name="expression-statement-c"></a>Оператор выражений (C)

Когда выполняется оператор-выражение, соответствующее выражение оценивается по правилам, описанным в статье [Выражения и присваивания](../c-language/expressions-and-assignments.md).

## <a name="syntax"></a>Синтаксис

*expression-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*expression*<sub>opt</sub> **;**

Все побочные эффекты от вычисления выражений выполняются до перехода к следующему оператору. Пустой оператор выражения называется неопределенным оператором. Дополнительные сведения см. в статье [Оператор NULL (C)](../c-language/null-statement-c.md).

В следующих примерах демонстрируются операторы выражения.

```C
x = ( y + 3 );            /* x is assigned the value of y + 3  */
x++;                      /* x is incremented                  */
x = y = 0;                /* Both x and y are initialized to 0 */
proc( arg1, arg2 );       /* Function call returning void      */
y = z = ( f( x ) + 3 );   /* A function-call expression        */
```

В последней строке приводится пример выражения вызова функции. Значение этого выражения (т. е. значение, возвращаемое функцией) увеличивается на 3, а затем присваивается обеим переменным: `y` и `z`.

## <a name="see-also"></a>См. также

[Операторы](../c-language/statements-c.md)
