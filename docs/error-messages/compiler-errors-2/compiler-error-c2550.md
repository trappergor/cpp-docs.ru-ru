---
title: Ошибка компилятора C2550
ms.date: 11/04/2016
f1_keywords:
- C2550
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
ms.openlocfilehash: 2df6ae70be31bc519e6cfd826646073becf1ad61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462677"
---
# <a name="compiler-error-c2550"></a>Ошибка компилятора C2550

«Идентификатор»: список инициализации конструктора допустимы только в месте определения конструктора

Список инициализаторов базового класса используется в определении функции, которая не является конструктором.

Следующий пример приводит к возникновению ошибки C2550:

```
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