---
title: Оператор dynamic_cast
ms.date: 11/04/2016
f1_keywords:
- dynamic_cast_cpp
helpviewer_keywords:
- dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
ms.openlocfilehash: 75085fe6dd1478fee769e23938c55c6300429d86
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529159"
---
# <a name="dynamiccast-operator"></a>Оператор dynamic_cast

Преобразует операнд `expression` в объект типа `type-id`.

## <a name="syntax"></a>Синтаксис

```
dynamic_cast < type-id > ( expression )
```

## <a name="remarks"></a>Примечания

Параметр `type-id` должен быть указателем или ссылкой на ранее определенный тип класса или "указателем на void". Тип операнда `expression` должен быть указателем, если `type-id` является указателем, или l-значением, если `type-id` является ссылкой.

См. в разделе [static_cast](../cpp/static-cast-operator.md) объяснение различий между преобразованиями путем приведения статический и динамический, а также при необходимости использовать каждый.

Существуют два критические изменения в поведении **dynamic_cast** в управляемом коде:

- **dynamic_cast** в указатель на базовый тип упакованного перечисления приведет к сбою во время выполнения, возвращая 0 вместо преобразованного указателя.

- **dynamic_cast** больше не будет создано исключение при `type-id` является внутренним указателем на тип значения, с чего приведение вызывает сбой во время выполнения.  Приведение теперь возвращает значение указателя 0, а исключение не создается.

Если `type-id` является указателем на однозначно доступный прямой или косвенный базовый класс операнда `expression`, то результатом будет указатель на уникальный подобъект типа `type-id`. Пример:

```cpp
// dynamic_cast_1.cpp
// compile with: /c
class B { };
class C : public B { };
class D : public C { };

void f(D* pd) {
   C* pc = dynamic_cast<C*>(pd);   // ok: C is a direct base class
                                   // pc points to C subobject of pd
   B* pb = dynamic_cast<B*>(pd);   // ok: B is an indirect base class
                                   // pb points to B subobject of pd
}
```

Этот тип преобразования называется "восходящим приведением типа", поскольку при нем указатель перемещается вверх по иерархии классов: от производного класса к классу, от которого он является производным. Восходящее приведение типа является неявным преобразованием.

Если `type-id` является указателем void*, выполняется проверка во время выполнения, чтобы определить фактический тип операнда `expression`. Результатом является указатель на полный объект, на который указывает операнд `expression`. Пример:

```cpp
// dynamic_cast_2.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};

void f() {
   A* pa = new A;
   B* pb = new B;
   void* pv = dynamic_cast<void*>(pa);
   // pv now points to an object of type A

   pv = dynamic_cast<void*>(pb);
   // pv now points to an object of type B
}
```

Если `type-id` не является указателем void*, то выполняется проверка во время выполнения, чтобы определить, может ли объект, на который указывает операнд `expression`, быть преобразован в тип, указанный параметром `type-id`.

Если тип операнда `expression` является базовым классом типа, заданного параметром `type-id`, то выполняется проверка во время выполнения, чтобы определить, указывает ли операнд `expression` на полный объект типа, заданного параметром `type-id`. Если это так, то результатом является указатель на полный объект типа, заданного параметром `type-id`. Пример:

```cpp
// dynamic_cast_3.cpp
// compile with: /c /GR
class B {virtual void f();};
class D : public B {virtual void f();};

void f() {
   B* pb = new D;   // unclear but ok
   B* pb2 = new B;

   D* pd = dynamic_cast<D*>(pb);   // ok: pb actually points to a D
   D* pd2 = dynamic_cast<D*>(pb2);   // pb2 points to a B not a D
}
```

Этот тип преобразования называется "нисходящим приведением типа", поскольку при нем указатель перемещается вниз по иерархии классов: от заданного класса к производному от него классу.

В случаях множественного наследования возникают возможности для неоднозначности. Рассмотрим для примера иерархию классов, показанную на следующем рисунке.

Для типов CLR **dynamic_cast** приведет к холостой Если преобразование может выполняться неявно или MSIL `isinst` инструкция, которая выполняет динамическую проверку и возвращает **nullptr** Если Преобразование завершается неудачей.

В следующем примере используется **dynamic_cast** для определения, является ли класс экземпляром определенного типа:

```cpp
// dynamic_cast_clr.cpp
// compile with: /clr
using namespace System;

void PrintObjectType( Object^o ) {
   if( dynamic_cast<String^>(o) )
      Console::WriteLine("Object is a String");
   else if( dynamic_cast<int^>(o) )
      Console::WriteLine("Object is an int");
}

int main() {
   Object^o1 = "hello";
   Object^o2 = 10;

   PrintObjectType(o1);
   PrintObjectType(o2);
}
```

![Иерархии, показывающая множественное наследование классов](../cpp/media/vc39011.gif "vc39011") класс иерархии показывающая множественное наследование

Указатель на объект типа `D` можно безопасно привести к `B` или `C`. Однако если в результате приведения `D` указывает на объект `A`, какой экземпляр объекта `A` будет являться результатом? Это может привести к ошибке неоднозначного приведения. Чтобы обойти эту проблему, можно выполнить два однозначных приведения. Пример:

```cpp
// dynamic_cast_4.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};
class D : public B {virtual void f();};

void f() {
   D* pd = new D;
   B* pb = dynamic_cast<B*>(pd);   // first cast to B
   A* pa2 = dynamic_cast<A*>(pb);   // ok: unambiguous
}
```

При использовании виртуальных базовых классов могут возникать дополнительные неоднозначности. Рассмотрим для примера иерархию классов, показанную на следующем рисунке.

![Иерархия, показывающая виртуальные базовые классы класса](../cpp/media/vc39012.gif "vc39012") класс иерархии отображаются виртуальные базовые классы

В этой иерархии объект `A` является виртуальным базовым классом. Заданный экземпляр класса `E` и указатель на `A` подобъект **dynamic_cast** в указатель на `B` завершится ошибкой из-за неоднозначности. Необходимо сначала выполнить обратное приведение к полному объекту `E`, затем однозначным образом вернуться вверх по иерархии, чтобы дойти до нужного объекта `B`.

Рассмотрим для примера иерархию классов, показанную на следующем рисунке.

![Иерархии, показывающая повторяющиеся базовые классы классов](../cpp/media/vc39013.gif "vc39013") класс иерархии показывающая повторяющиеся базовые классы

При использовании заданного объекта типа `E` и указателя на подобъект `D` можно выполнить три преобразования, чтобы перейти от подобъекта `D` к крайнему слева подобъекту `A`. Можно выполнять **dynamic_cast** преобразование из `D` указатель на `E` указатель, а затем преобразование (либо **dynamic_cast** или неявное преобразование) из `E`для `B`и наконец неявное преобразование из `B` для `A`. Пример:

```cpp
// dynamic_cast_5.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A { };
class D {virtual void f();};
class E : public B, public C, public D {virtual void f();};

void f(D* pd) {
   E* pe = dynamic_cast<E*>(pd);
   B* pb = pe;   // upcast, implicit conversion
   A* pa = pb;   // upcast, implicit conversion
}
```

**Dynamic_cast** оператор может также использоваться для выполнения «перекрестного приведения». В иерархии классов из предыдущего примера можно выполнить приведение указателя, например, из подобъекта `B` в подобъект `D`, если полный объект имеет тип `E`.

С учетом перекрестного приведения можно выполнить преобразование из указателя на объект `D` в крайний левый подобъект `A` всего за два шага. Можно перекрестное приведение из `D` в `B`, а затем неявное преобразование из `B` в `A`. Пример:

```cpp
// dynamic_cast_6.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A { };
class D {virtual void f();};
class E : public B, public C, public D {virtual void f();};

void f(D* pd) {
   B* pb = dynamic_cast<B*>(pd);   // cross cast
   A* pa = pb;   // upcast, implicit conversion
}
```

Значение пустого указателя преобразуется в значение пустого указателя конечного типа, **dynamic_cast**.

Если при использовании оператора `dynamic_cast < type-id > ( expression )` невозможно точно преобразовать операнд `expression` в тип `type-id`, то проверка во время выполнения приводит к сбою приведения. Пример:

```cpp
// dynamic_cast_7.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};

void f() {
   A* pa = new A;
   B* pb = dynamic_cast<B*>(pa);   // fails at runtime, not safe;
   // B not derived from A
}
```

Значением приведения к типу указателя, которое привело к сбою, является пустой указатель. Ошибки приведения к типу возникает исключение ссылки [исключение bad_cast](../cpp/bad-cast-exception.md).   Если `expression` указывает и не ссылается на допустимый объект `__non_rtti_object` возникает исключение.

См. в разделе [typeid](../cpp/typeid-operator.md) объяснение `__non_rtti_object` исключение.

## <a name="example"></a>Пример

В следующем примере создается указатель базового класса (структура A) на объект (структура C).  Это (а также тот факт, что они являются виртуальными функциями) порождает полиморфизм времени выполнения.

В этом примере также вызывается невиртуальная функция в иерархии.

```cpp
// dynamic_cast_8.cpp
// compile with: /GR /EHsc
#include <stdio.h>
#include <iostream>

struct A {
    virtual void test() {
        printf_s("in A\n");
   }
};

struct B : A {
    virtual void test() {
        printf_s("in B\n");
    }

    void test2() {
        printf_s("test2 in B\n");
    }
};

struct C : B {
    virtual void test() {
        printf_s("in C\n");
    }

    void test2() {
        printf_s("test2 in C\n");
    }
};

void Globaltest(A& a) {
    try {
        C &c = dynamic_cast<C&>(a);
        printf_s("in GlobalTest\n");
    }
    catch(std::bad_cast) {
        printf_s("Can't cast to C\n");
    }
}

int main() {
    A *pa = new C;
    A *pa2 = new B;

    pa->test();

    B * pb = dynamic_cast<B *>(pa);
    if (pb)
        pb->test2();

    C * pc = dynamic_cast<C *>(pa2);
    if (pc)
        pc->test2();

    C ConStack;
    Globaltest(ConStack);

   // will fail because B knows nothing about C
    B BonStack;
    Globaltest(BonStack);
}
```

```Output
in C
test2 in B
in GlobalTest
Can't cast to C
```

## <a name="see-also"></a>См. также

[Операторы приведения](../cpp/casting-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)