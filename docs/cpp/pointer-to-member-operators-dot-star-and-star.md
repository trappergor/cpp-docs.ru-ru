---
title: 'Операторы указателей на члены: .* и -&gt;*'
ms.date: 11/04/2016
f1_keywords:
- .*
- ->*
helpviewer_keywords:
- expressions [C++], pointer
- pointer-to-member operators [C++]
- .* operator
- expressions [C++], operators
- ->* operator
ms.assetid: 2632be3f-1c81-4523-b56c-982a92a68688
ms.openlocfilehash: 60dad0e3134662957ee21396d330af795e80918e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267667"
---
# <a name="pointer-to-member-operators--and--gt"></a>Операторы указателей на члены: .* и -&gt;*

## <a name="syntax"></a>Синтаксис

```
expression .* expression
expression ->* expression
```

## <a name="remarks"></a>Примечания

Операторы указателя на член,. * и ->\*, возвращают значение конкретного члена класса для объекта, указанного в левой части выражения.  Правая часть должна определять член класса.  В следующем примере показано использование этих операторов.

```cpp
// expre_Expressions_with_Pointer_Member_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

class Testpm {
public:
   void m_func1() { cout << "m_func1\n"; }
   int m_num;
};

// Define derived types pmfn and pmd.
// These types are pointers to members m_func1() and
// m_num, respectively.
void (Testpm::*pmfn)() = &Testpm::m_func1;
int Testpm::*pmd = &Testpm::m_num;

int main() {
   Testpm ATestpm;
   Testpm *pTestpm = new Testpm;

// Access the member function
   (ATestpm.*pmfn)();
   (pTestpm->*pmfn)();   // Parentheses required since * binds
                        // less tightly than the function call.

// Access the member data
   ATestpm.*pmd = 1;
   pTestpm->*pmd = 2;

   cout  << ATestpm.*pmd << endl
         << pTestpm->*pmd << endl;
   delete pTestpm;
}
```

## <a name="output"></a>Вывод

```Output
m_func1
m_func1
1
2
```

В приведенном выше примере указатель на член, `pmfn`, используется для вызова функции-члена `m_func1`. Другой указатель на член, `pmd`, используется для обращения к члену `m_num`.

Бинарный оператор .* объединяет свой первый операнд, который должен быть объектом типа класса, со своим вторым операндом, который должен иметь тип указателя на член.

Бинарный оператор -> * объединяет свой первый операнд, который должен быть указатель на объект типа класса, со своим вторым операндом, который должен быть типом указателя на член.

В выражении с оператором .* первый операнд должен относиться к тому же типу класса, что и указатель на член, заданный во втором операнде (и быть доступным для него), или иметь доступный тип, однозначно производный от этого класса и доступный для него.

В выражении, содержащем-> * первый операнд должен быть типа «указатель на тип класса» тип указан во втором операнде оператора, или он должен быть типа однозначно производным от этого класса.

## <a name="example"></a>Пример

Рассмотрим следующие классы и фрагмент программы:

```cpp
// expre_Expressions_with_Pointer_Member_Operators2.cpp
// C2440 expected
class BaseClass {
public:
   BaseClass(); // Base class constructor.
   void Func1();
};

// Declare a pointer to member function Func1.
void (BaseClass::*pmfnFunc1)() = &BaseClass::Func1;

class Derived : public BaseClass {
public:
   Derived();  // Derived class constructor.
   void Func2();
};

// Declare a pointer to member function Func2.
void (Derived::*pmfnFunc2)() = &Derived::Func2;

int main() {
   BaseClass ABase;
   Derived ADerived;

   (ABase.*pmfnFunc1)();   // OK: defined for BaseClass.
   (ABase.*pmfnFunc2)();   // Error: cannot use base class to
                           // access pointers to members of
                           // derived classes.

   (ADerived.*pmfnFunc1)();   // OK: Derived is unambiguously
                              // derived from BaseClass.
   (ADerived.*pmfnFunc2)();   // OK: defined for Derived.
}
```

Результат. * или ->\* операторов указателя на член является объект или функция типа, указанного в объявлении указателя на член. Таким образом, в предыдущем примере результатом выражения `ADerived.*pmfnFunc1()` является указатель на функцию, которая не возвращает значения (void). Если второй операнд имеет l-значение, то и результатом будет l-значение.

> [!NOTE]
>  Если результатом одного из операторов указателя на член является функция, то результат может использоваться только как операнд к оператору вызова функции.

## <a name="see-also"></a>См. также

[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)