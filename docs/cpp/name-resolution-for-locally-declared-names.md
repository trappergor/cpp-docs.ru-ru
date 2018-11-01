---
title: Разрешение локально объявленных имен
ms.date: 11/04/2016
ms.assetid: 743b88f3-de11-48f4-ae83-931449ea3886
ms.openlocfilehash: 91ed065a6c8aca6c7f740f0236cb13c8133fc96f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602557"
---
# <a name="name-resolution-for-locally-declared-names"></a>Разрешение локально объявленных имен

Можно создать ссылку на само имя шаблона с аргументами шаблона или без них. В области шаблона класса само имя относится к шаблону. В области специализации шаблона или частичной специализации само имя относится к специализации или частичной специализации. Можно также создать ссылки на другие специализации или частичные специализации шаблона с использованием соответствующих аргументов шаблона.

## <a name="example"></a>Пример

Следующий фрагмент кода показывает, что имя А шаблона классов интерпретируется по-разному в области видимости специализации или частичной специализации.

```cpp
// template_name_resolution3.cpp
// compile with: /c
template <class T> class A {
   A* a1;   // A refers to A<T>
   A<int>* a2;  // A<int> refers to a specialization of A.
   A<T*>* a3;   // A<T*> refers to the partial specialization A<T*>.
};

template <class T> class A<T*> {
   A* a4; // A refers to A<T*>.
};

template<> class A<int> {
   A* a5; // A refers to A<int>.
};
```

## <a name="example"></a>Пример

В случае конфликта имен между параметром шаблона и другим объектом параметр шаблона может быть скрыт, но это не обязательно. Следующие правила помогут определить приоритет.

Параметр шаблона находится в области видимости из точки, где он впервые появляется, и до конца класса или шаблона функции. Если имя снова отображается в списке аргументов шаблона или в списке базовых классов, оно относится к тому же типу. В стандартном языке C++ невозможно объявить в той же области видимости никакое другое имя, идентичное параметру шаблона. Расширение Microsoft позволяет переопределять параметр шаблона в области видимости шаблона. В следующем примере показано использование параметра шаблона в базовой спецификации шаблона класса.

```cpp
// template_name_resolution4.cpp
// compile with: /EHsc
template <class T>
class Base1 {};

template <class T>
class Derived1 : Base1<T> {};

int main() {
   // Derived1<int> d;
}
```

## <a name="example"></a>Пример

При определении функций-членов шаблона за пределами шаблона классов можно использовать другое имя параметра шаблонов. Если в определении функции-члена шаблона используется другое имя параметра шаблона, нежели в декларации, а имя, используемое в определении, конфликтует с другим элементом объявления, приоритет получает элемент в объявлении шаблона.

```cpp
// template_name_resolution5.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class T> class C {
public:
   struct Z {
      Z() { cout << "Z::Z()" << endl; }
   };
   void f();
};

template <class Z>
void C<Z>::f() {
   // Z refers to the struct Z, not to the template arg;
   // Therefore, the constructor for struct Z will be called.
   Z z;
}

int main() {
   C<int> c;
   c.f();
}
```

```Output
Z::Z()
```

## <a name="example"></a>Пример

При определении функции шаблона или функции-члена за пределами пространства имен, в котором объявлен шаблон, аргумент шаблона имеет приоритет над именами других элементов пространства имен.

```cpp
// template_name_resolution6.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

namespace NS {
   void g() { cout << "NS::g" << endl; }

   template <class T> struct C {
      void f();
      void g() { cout << "C<T>::g" << endl; }
   };
};

template <class T>
void NS::C<T>::f() {
   g(); // C<T>::g, not NS::g
};

int main() {
   NS::C<int> c;
   c.f();
}
```

```Output
C<T>::g
```

## <a name="example"></a>Пример

Если класс шаблона в определениях вне объявления класса шаблонов имеет базовый класс, который не зависит от аргумента шаблона и если базовый класс или один из его элементов имеют то же имя, что и аргумент шаблона, имя базового класса или элемента скрывает аргумент шаблона.

```cpp
// template_name_resolution7.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

struct B {
   int i;
   void print() { cout << "Base" << endl; }
};

template <class T, int i> struct C : public B {
   void f();
};

template <class B, int i>
void C<B, i>::f() {
   B b;   // Base class b, not template argument.
   b.print();
   i = 1; // Set base class's i to 1.
}

int main() {
   C<int, 1> c;
   c.f();
   cout << c.i << endl;
}
```

```Output
Base
1
```

## <a name="see-also"></a>См. также

[Разрешение имен](../cpp/templates-and-name-resolution.md)