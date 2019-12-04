---
title: Ошибка компилятора C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 7da9da2daedc79db619f82848dc864d1cb7bd1f1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750095"
---
# <a name="compiler-error-c3531"></a>Ошибка компилятора C3531

"символ": символ, тип которого содержит "Auto", должен иметь инициализатор

Указанная переменная не содержит выражение инициализатора.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Укажите выражение инициализатора, например простое присваивание, использующее синтаксис равенства-знака, при объявлении переменной.

## <a name="example"></a>Пример

В следующем примере выдается C3531, так как переменные `x1`, `y1, y2, y3`и `z2` не инициализированы.

```cpp
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

## <a name="see-also"></a>См. также:

[Ключевое слово auto](../../cpp/auto-keyword.md)
