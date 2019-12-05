---
title: Пример вызова. Прототип и вызов функции
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: cbe9ee16db502c9e27dcbd74da4ef6a85f00960f
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857636"
---
# <a name="calling-example-function-prototype-and-call"></a>Пример вызова. Прототип и вызов функции

**Блок, относящийся только к системам Майкрософт**

В следующем примере показаны результаты вызова функции с использованием различных соглашений о вызовах.

Этот пример основан на следующей схеме функции. Замените `calltype` соответствующим соглашением о вызове.

```cpp
void    calltype MyFunc( char c, short s, int i, double f );
.
.
.
void    MyFunc( char c, short s, int i, double f )
    {
    .
    .
    .
    }
.
.
.
MyFunc ('x', 12, 8192, 2.7183);
```

Дополнительные сведения см. в разделе [результаты вызова примера](../cpp/results-of-calling-example.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Соглашения о вызовах](../cpp/calling-conventions.md)