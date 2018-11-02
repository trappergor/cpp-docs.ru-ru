---
title: Предупреждение компилятора (уровень 2) C4250
ms.date: 11/04/2016
f1_keywords:
- C4250
helpviewer_keywords:
- C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
ms.openlocfilehash: 8baf3c03c87dc70a80b785d7f81cbee4e1d828f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454864"
---
# <a name="compiler-warning-level-2-c4250"></a>Предупреждение компилятора (уровень 2) C4250

«класс1»: наследуется «класс 2::член» через превосходство

Два или более членов совпадают. Этому параметру в `class2` наследуется, поскольку он является базовым классом для других классов, содержащих этот член.

Чтобы скрыть C4250, используйте [предупреждение](../../preprocessor/warning.md) директивы pragma.

Так как виртуальный базовый класс является общим для нескольких производных классов, имя в производном классе превосходит имя в базовом классе. Например, учитывая следующие иерархии классов, существует два определения функции, унаследованной в рамках ромбовидной: экземпляр структуры через слабый класс и поиска доминантного:: func() главного класса. Вызов func() объект класса ромб, всегда вызывает метод экземпляра dominate::func().  Если экземпляр func() слабый класс, ни будет доминировать определение и вызов отмечается как неоднозначная.

```
// C4250.cpp
// compile with: /c /W2
#include <stdio.h>
struct vbc {
   virtual void func() { printf("vbc::func\n"); }
};

struct weak : public virtual vbc {};

struct dominant : public virtual vbc {
   void func() { printf("dominant::func\n"); }
};

struct diamond : public weak, public dominant {};

int main() {
   diamond d;
   d.func();   // C4250
}
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4250.

```
// C4250_b.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;
class A {
public:
   virtual operator int () {
      return 2;
   }
};

class B : virtual public A {
public:
   virtual operator int () {
      return 3;
   }
};

class C : virtual public A {};

class E : public B, public C {};   // C4250

int main() {
   E eObject;
   cout << eObject.operator int() << endl;
}
```

## <a name="example"></a>Пример

В этом примере показано более сложная ситуация. Следующий пример приводит к возникновению ошибки C4250.

```
// C4250_c.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;

class V {
public:
   virtual int f() {
      return 1024;
   }
};

class B : virtual public V {
public:
   int b() {
      return f(); // B::b() calls V::f()
   }
};

class M : virtual public V {
public:
   int f() {
      return 7;
   }
};

// because of dominance, f() is M::f() inside D,
// changing the meaning of B::b's f() call inside a D
class D : public B, public M {};   // C4250

int main() {
   D d;
   cout << "value is: " << d.b();   // invokes M::f()
}
```