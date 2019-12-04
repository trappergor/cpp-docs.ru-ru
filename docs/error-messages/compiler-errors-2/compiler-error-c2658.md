---
title: Ошибка компилятора C2658
ms.date: 11/04/2016
f1_keywords:
- C2658
helpviewer_keywords:
- C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
ms.openlocfilehash: 77a9122d20561ceee4f211394b3b81900d5580ac
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756088"
---
# <a name="compiler-error-c2658"></a>Ошибка компилятора C2658

"член": переопределение в анонимной структуре или объединении

Две Анонимные структуры или объединения содержат объявления элементов с одинаковым идентификатором, но с разными типами. В режиме [/Za](../../build/reference/za-ze-disable-language-extensions.md)эта ошибка также возникает для членов с одинаковым идентификатором и типом.

Следующий пример приводит к возникновению ошибки C2658:

```cpp
// C2658.cpp
// compile with: /c
struct X {
   union { // can be struct too
      int i;
   };
   union {
      int i;   // Under /Za, C2658
      // int i not needed here because it is defined in the first union
   };
};

struct Z {
   union {
      char *i;
   };

   union {
      void *i;   // C2658 redefinition of 'i'
      // try the following line instead
      // void *ii;
   };
};
```
