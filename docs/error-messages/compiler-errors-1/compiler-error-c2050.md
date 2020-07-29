---
title: Ошибка компилятора c2050
ms.date: 11/04/2016
f1_keywords:
- C2050
helpviewer_keywords:
- C2050
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
ms.openlocfilehash: e2eb6f323b5ae377c42bee4ad6ff8d83a1d3c16b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221306"
---
# <a name="compiler-error-c2050"></a>Ошибка компилятора c2050

выражение switch не является целым

**`switch`** Результатом вычисления выражения является нецелочисленное значение. Чтобы устранить эту ошибку, используйте только целочисленные значения в операторах switch.

Следующий пример приводит к возникновению ошибки c2050:

```cpp
// C2050.cpp
int main() {
   int a = 1;
   switch ("a") {   // C2050
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```

Возможное решение:

```cpp
// C2050b.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```
