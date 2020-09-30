---
title: Ошибка компилятора C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 4537c6c76814f2aeb8f8d62579caec86785de252
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510143"
---
# <a name="compiler-error-c3531"></a>Ошибка компилятора C3531

"символ": символ, тип которого содержит "Auto", должен иметь инициализатор

Указанная переменная не содержит выражение инициализатора.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Укажите выражение инициализатора, например простое присваивание, использующее синтаксис равенства-знака, при объявлении переменной.

## <a name="example"></a>Пример

В следующем примере C3531 выдается, так как переменные `x1` , `y1, y2, y3` и `z2` не инициализируются.

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

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-cpp.md)
