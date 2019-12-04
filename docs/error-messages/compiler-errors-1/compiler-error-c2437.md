---
title: Ошибка компилятора C2437
ms.date: 11/04/2016
f1_keywords:
- C2437
helpviewer_keywords:
- C2437
ms.assetid: 2d2b3c6c-856a-4b27-ae10-64813b3e5483
ms.openlocfilehash: 745ab4f53223ec60e745068b1857206ed114086a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744346"
---
# <a name="compiler-error-c2437"></a>Ошибка компилятора C2437

"идентификатор": инициализация уже выполнена

Объект можно инициализировать только один раз.

Следующий пример приводит к возникновению ошибки C2437:

```cpp
// C2437.cpp
// compile with: /c
class A {
public:
   A(int i) {}
};

class B : A {
   B() : A(1), A(2) {}   // C2437
   B() : A(1) {}   // OK
};
```
