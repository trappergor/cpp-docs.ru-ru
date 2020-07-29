---
title: Ошибка компилятора C2048
ms.date: 11/04/2016
f1_keywords:
- C2048
helpviewer_keywords:
- C2048
ms.assetid: 44704726-85fc-42f0-afb9-194df8c4ca7c
ms.openlocfilehash: 483e4d706a1c08899e6cd6e1ec561a21ed805014
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87210440"
---
# <a name="compiler-error-c2048"></a>Ошибка компилятора C2048

несколько вариантов, используемых по умолчанию

**`switch`** Оператор содержит несколько **`default`** меток. Удалите одну из **`default`** меток, чтобы устранить эту ошибку.

В следующем примере возникает ошибка C2048:

```cpp
// C2048.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
      default:   // C2048
         a = 3;
   }
}
```

Возможное решение:

```cpp
// C2048b.cpp
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
