---
title: Пример вызова. Прототип функции и вызова
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: f89f4f1917810baa585dd1661428e0809b93cca0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345113"
---
# <a name="calling-example-function-prototype-and-call"></a>Пример вызова. Прототип функции и вызова

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

В следующем примере показаны результаты вызова функции с использованием различных соглашений о вызовах.

Этот пример основан на следующей схеме функции. Замените `calltype` соответствующим соглашением о вызове.

```
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

Дополнительные сведения см. в разделе [пример результатов вызова](../cpp/results-of-calling-example.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Соглашения о вызовах](../cpp/calling-conventions.md)