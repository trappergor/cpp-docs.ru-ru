---
title: Ошибка компилятора C2881
ms.date: 11/04/2016
f1_keywords:
- C2881
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
ms.openlocfilehash: 9c171fd529943bb07a6c512e4ac97f64f13f959d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736286"
---
# <a name="compiler-error-c2881"></a>Ошибка компилятора C2881

"имен1": уже используется как псевдоним для "имен2"

Нельзя использовать то же имя, что и псевдоним для двух пространств имен.

Следующий пример приводит к возникновению ошибки C2881:

```cpp
// C2881.cpp
// compile with: /c
namespace A {
   int k;
}

namespace B {
   int i;
}

namespace C = A;
namespace C = B;   // C2881 C is already an alias for A
```
