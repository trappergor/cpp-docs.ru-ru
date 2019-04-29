---
title: Ошибка компилятора C2550
ms.date: 11/04/2016
f1_keywords:
- C2550
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
ms.openlocfilehash: 2df6ae70be31bc519e6cfd826646073becf1ad61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353356"
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