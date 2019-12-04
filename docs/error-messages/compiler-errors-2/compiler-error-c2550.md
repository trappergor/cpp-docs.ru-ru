---
title: Ошибка компилятора C2550
ms.date: 11/04/2016
f1_keywords:
- C2550
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
ms.openlocfilehash: 29e907e682e0caae86569fe8bd7c101b3e0b14a3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740823"
---
# <a name="compiler-error-c2550"></a>Ошибка компилятора C2550

"идентификатор": списки инициализаторов конструктора разрешены только в определениях конструктора

Список инициализации базового класса используется в определении функции, которая не является конструктором.

Следующий пример приводит к возникновению ошибки C2550:

```cpp
// C2550.cpp
// compile with: /c
class C {
public:
   C();
};

class D : public C {
public:
   D();
   void func();
};

void D::func() : C() {}  // C2550
D::D() : C() {}   // OK
```
