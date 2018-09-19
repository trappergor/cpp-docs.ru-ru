---
title: Ошибка компилятора C3531 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3531
dev_langs:
- C++
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 375eb419e3f2f492df328a964eeb1bb77bc0d5dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106854"
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