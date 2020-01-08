---
title: 'Оператор вызова функции: ()'
ms.date: 11/04/2016
helpviewer_keywords:
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
ms.openlocfilehash: 3194c34bacfe7b2ed758ab245c5858eadb18e64e
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301526"
---
# <a name="function-call-operator-"></a>Оператор вызова функции: ()

Постфиксное выражение, за которым следует оператор вызова функции **()** , задает вызов функции.

## <a name="syntax"></a>Синтаксис

```
postfix-expression
( [argument-expression-list ] )
```

## <a name="remarks"></a>Заметки

Аргументы оператора вызова функции — ноль или более выражений, разделенных запятыми. Эти выражения являются фактическими аргументами функции.

*Постфиксный выражение* должен возвращать адрес функции (например, идентификатор функции или значение указателя на функцию), а *аргумент-expression-list* — список выражений (разделенных запятыми), значения которых (аргументы) передаются в функцию. Аргумент *argument-expression-list* может быть пустым.

*Постфиксный выражение* должен иметь один из следующих типов:

- Функция, возвращающая тип `T`. Пример объявления:

    ```cpp
    T func( int i )
    ```

- Указатель на функцию, возвращающую тип `T`. Пример объявления:

    ```cpp
    T (*func)( int i )
    ```

- Ссылка на функцию, возвращающую тип `T`. Пример объявления:

    ```cpp
    T (&func)(int i)
    ```

- Разыменование функции указателя на член, возвращающее тип `T`. Примеры вызовов функции:

    ```cpp
    (pObject->*pmf)();
    (Object.*pmf)();
    ```

## <a name="example"></a>Пример

В следующем примере вызывается функция стандартной библиотеки `strcat_s` с тремя аргументами:

```cpp
// expre_Function_Call_Operator.cpp
// compile with: /EHsc

#include <iostream>
#include <string>

// C++ Standard Library name space
using namespace std;

int main()
{
    enum
    {
        sizeOfBuffer = 20
    };

    char s1[ sizeOfBuffer ] = "Welcome to ";
    char s2[ ] = "C++";

    strcat_s( s1, sizeOfBuffer, s2 );

    cout << s1 << endl;
}
```

```Output
Welcome to C++
```

## <a name="function-call-results"></a>Результаты вызова функции

Вызов функции возвращает r-значение, если функция не объявлена как ссылочный тип. Функции с ссылочным типом возвращаемого значения возвращают l-значение и могут использоваться в левой части оператора присваивания следующим образом.

```cpp
// expre_Function_Call_Results.cpp
// compile with: /EHsc
#include <iostream>
class Point
{
public:
    // Define "accessor" functions as
    // reference types.
    unsigned& x() { return _x; }
    unsigned& y() { return _y; }
private:
    unsigned _x;
    unsigned _y;
};

using namespace std;
int main()
{
    Point ThePoint;

    ThePoint.x() = 7;           // Use x() as an l-value.
    unsigned y = ThePoint.y();  // Use y() as an r-value.

    // Use x() and y() as r-values.
    cout << "x = " << ThePoint.x() << "\n"
         << "y = " << ThePoint.y() << "\n";
}
```

Приведенный выше код определяет класс с именем `Point`, который содержит закрытые объекты данных, представляющие координаты *x* и *y* . Эти объекты данных необходимо изменить, а значения — извлечь. Программа — это лишь одно из нескольких решений для такого класса. Также можно использовать функции `GetX` и `SetX` или `GetY` и `SetY`.

Функции, возвращающие типы классов, указатели на типы классов или ссылки на типы классов можно использовать как левый операнд в операторах выбора члена. Поэтому следующий код допустим.

```cpp
// expre_Function_Results2.cpp
class A {
public:
   A() {}
   A(int i) {}
   int SetA( int i ) {
      return (I = i);
   }

   int GetA() {
      return I;
   }

private:
   int I;
};

A func1() {
   A a = 0;
   return a;
}

A* func2() {
   A *a = new A();
   return a;
}

A& func3() {
   A *a = new A();
   A &b = *a;
   return b;
}

int main() {
   int iResult = func1().GetA();
   func2()->SetA( 3 );
   func3().SetA( 7 );
}
```

Функции можно вызывать рекурсивно. Дополнительные сведения об объявлениях функций см. в разделе [функции](functions-cpp.md). Связанные материалы относятся к [единицам трансляции и компоновке](../cpp/program-and-linkage-cpp.md).

## <a name="see-also"></a>См. также:

[Постфиксные выражения](../cpp/postfix-expressions.md)<br/>
[Операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Вызов функции](../c-language/function-call-c.md)