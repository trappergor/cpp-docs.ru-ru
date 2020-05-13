---
title: Оператор dynamic_cast
description: Общие сведения об C++ операторе Language dynamic_cast.
ms.date: 02/03/2020
f1_keywords:
- dynamic_cast_cpp
helpviewer_keywords:
- dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
ms.openlocfilehash: d12b338b4b52d81b01097a1e1f5c83ec10eac774
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189498"
---
# <a name="dynamic_cast-operator"></a>Оператор dynamic_cast

Преобразует операнд `expression` в объект типа `type-id`.

## <a name="syntax"></a>Синтаксис

```
dynamic_cast < type-id > ( expression )
```

## <a name="remarks"></a>Remarks

Параметр `type-id` должен быть указателем или ссылкой на ранее определенный тип класса или "указателем на void". Тип операнда `expression` должен быть указателем, если `type-id` является указателем, или l-значением, если `type-id` является ссылкой.

Описание различий между преобразованиями статического и динамического приведения см. в разделе [static_cast](../cpp/static-cast-operator.md) .

Существует два критических изменения в работе **dynamic_cast** в управляемом коде:

- **dynamic_cast** указатель на базовый тип упакованного перечисления произойдет сбой во время выполнения, возвращая 0 вместо преобразованного указателя.

- **dynamic_cast** больше не создает исключение, когда `type-id` является внутренним указателем на тип значения, при этом операция приведения завершается сбоем во время выполнения.  Приведение теперь возвращает значение указателя 0, а исключение не создается.

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

Для типов CLR **dynamic_cast** , если преобразование можно выполнить неявно, или инструкцию MSIL `isinst`, которая выполняет динамическую проверку и возвращает **nullptr** , если преобразование выполнить не удалось.

В следующем примере **dynamic_cast** используется для определения того, является ли класс экземпляром определенного типа:

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

![Иерархия классов, показывающая множественное наследование](../cpp/media/vc39011.gif "Иерархия классов, показывающая множественное наследование") <br/>
Иерархия классов, показывающая множественное наследование

Указатель на объект типа `D` можно безопасно привести к `B` или `C`. Однако если в результате приведения `D` указывает на объект `A`, какой экземпляр объекта `A` будет являться результатом? Это может привести к ошибке неоднозначного приведения. Чтобы обойти эту проблему, можно выполнить два однозначных приведения. Пример:

```cpp
// dynamic_cast_4.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A {virtual void f();};
class D : public B, public C {virtual void f();};

void f() {
   D* pd = new D;
   A* pa = dynamic_cast<A*>(pd);   // C4540, ambiguous cast fails at runtime
   B* pb = dynamic_cast<B*>(pd);   // first cast to B
   A* pa2 = dynamic_cast<A*>(pb);   // ok: unambiguous
}
```

При использовании виртуальных базовых классов могут возникать дополнительные неоднозначности. Рассмотрим для примера иерархию классов, показанную на следующем рисунке.

![Иерархия классов, показывающая виртуальные базовые классы](../cpp/media/vc39012.gif "Иерархия классов, показывающая виртуальные базовые классы") <br/>
Иерархия классов, показывающая виртуальные базовые классы

В этой иерархии объект `A` является виртуальным базовым классом. При наличии экземпляра класса `E` и указателя на `A` подобъект **dynamic_cast** указатель на `B` завершится ошибкой из-за неоднозначности. Необходимо сначала выполнить обратное приведение к полному объекту `E`, затем однозначным образом вернуться вверх по иерархии, чтобы дойти до нужного объекта `B`.

Рассмотрим для примера иерархию классов, показанную на следующем рисунке.

![Иерархия классов, показывающая дубликаты базовых классов](../cpp/media/vc39013.gif "Иерархия классов, показывающая повторяющиеся базовые классы") <br/>
Иерархия классов, показывающая повторяющиеся базовые классы

При использовании заданного объекта типа `E` и указателя на подобъект `D` можно выполнить три преобразования, чтобы перейти от подобъекта `D` к крайнему слева подобъекту `A`. Можно выполнить **dynamic_cast** преобразование из указателя `D` в указатель `E`, затем преобразование ( **dynamic_cast** или неявное преобразование) из `E` в `B`и, наконец, неявное преобразование из `B` в `A`. Пример:

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

Оператор **dynamic_cast** также можно использовать для выполнения перекрестного приведения. В иерархии классов из предыдущего примера можно выполнить приведение указателя, например, из подобъекта `B` в подобъект `D`, если полный объект имеет тип `E`.

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

Значение указателя NULL преобразуется в значение нулевого указателя конечного типа по **dynamic_cast**.

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

Значением приведения к типу указателя, которое привело к сбою, является пустой указатель. Неудачное приведение к ссылочному типу вызывает [исключение bad_cast](../cpp/bad-cast-exception.md).   Если `expression` не указывает на допустимый объект или ссылается на него, возникает исключение `__non_rtti_object`.

Описание исключения `__non_rtti_object` см. в разделе [typeid](../cpp/typeid-operator.md) .

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

## <a name="see-also"></a>См. также раздел

[Операторы приведения](../cpp/casting-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
