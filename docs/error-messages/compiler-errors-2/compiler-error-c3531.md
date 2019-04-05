---
title: Ошибка компилятора C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 6961d99d1a0d7d0ea063aee5544a1009af2547c7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031265"
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