---
title: Ошибка компилятора C2602
ms.date: 11/04/2016
f1_keywords:
- C2602
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
ms.openlocfilehash: da38600ea099c9b0d73e929a100a8c338bd3388f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466356"
---
# <a name="compiler-error-c2602"></a>Ошибка компилятора C2602

«класс::идентификатор» не является членом базового класса «class»

`Identifier` может быть недоступна, так как он не является членом, унаследованным от базового класса.

Следующий пример приводит к возникновению ошибки C2602:

```
// C2602.cpp
// compile with: /c
struct X {
   int x;
};
struct A {
   int a;
};
struct B : public A {
   X::x;   // C2602 B is not derived from X
   A::a;   // OK
};
```