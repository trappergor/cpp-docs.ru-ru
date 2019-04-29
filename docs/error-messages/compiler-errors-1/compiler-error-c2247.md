---
title: Ошибка компилятора C2247
ms.date: 11/04/2016
f1_keywords:
- C2247
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
ms.openlocfilehash: ab1f83e2075128441cbffd2d939e3b99b45be4c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301374"
---
# <a name="compiler-error-c2247"></a>Ошибка компилятора C2247

«Идентификатор» не доступен, поскольку «класс» использует «спецификатор» наследовать «class»

`identifier` наследуется от класса, объявленного с доступом к закрытым или защищенным.

Следующий пример приводит к возникновению ошибки C2247:

```
// C2247.cpp
class A {
public:
   int i;
};
class B : private A {};    // B inherits a private A
class C : public B {} c;   // so even though C's B is public
int j = c.i;               // C2247, i not accessible
```

Эта ошибка также может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: доступ к элементу управления с помощью защищенных членов. Защищенный член (n) может осуществляться только через функцию-член класса (B), который наследует от класса (A), членом которой он (n) является.

Для кода, который является допустимым в версиях Visual C++ в Visual Studio .NET и Visual Studio .NET 2003 объявление члена как дружественный элемент для типа. Также может использоваться открытое наследование.

```
// C2247b.cpp
// compile with: /c
// C2247 expected
class A {
public:
   void f();
   int n;
};

class B: protected A {
   // Uncomment the following line to resolve.
   // friend void A::f();
};

void A::f() {
   B b;
   b.n;
}
```

C2247 также может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: закрытые базовые классы становятся недоступны. Класс (A), который является закрытого базового класса к типу (B) необходимо недоступен типу (C), использующий B в качестве базового класса.

Для кода, который является допустимым в версиях Visual C++ в Visual Studio .NET и Visual Studio .NET 2003 используйте оператор области действия.

```
// C2247c.cpp
// compile with: /c
struct A {};

struct B: private A {};

struct C : B {
   void f() {
      A *p1 = (A*) this;   // C2247
      // try the following line instead
      // ::A *p2 = (::A*) this;
   }
};
```