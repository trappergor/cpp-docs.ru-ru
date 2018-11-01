---
title: Ошибка компилятора C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 0f6094daddf40b0899dc7f341f50a31daf7a999b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435455"
---
# <a name="compiler-error-c3531"></a>Ошибка компилятора C3531

«символ»: символ, тип которого содержит «auto» должен иметь инициализатор

Указанная переменная не имеет выражения инициализатора.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Укажите выражение инициализатора, например простое присваивание, который использует синтаксис со знаком равенства, при объявлении переменной.

## <a name="example"></a>Пример

Следующий пример вызывает ошибку C3531, поскольку переменные `x1`, `y1, y2, y3`, и `z2` не инициализируются.

```
// C3531.cpp
// Compile with /Zc:auto
int main()
{
   auto x1;                  // C3531
   auto y1, y2, y3;          // C3531
   auto z1 = 1, z2, z3 = -1; // C3531
   return 0;
}
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)