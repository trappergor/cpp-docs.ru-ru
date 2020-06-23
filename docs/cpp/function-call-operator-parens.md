---
title: 'Оператор вызова функции: ()'
ms.date: 06/11/2020
helpviewer_keywords:
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
no-loc:
- opt
ms.openlocfilehash: 59fd36a5ae135c55813019f04b0f5df4be2800b3
ms.sourcegitcommit: 2d7550d0f375aafa428ef0fb2e3962e4232be28e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "84777309"
---
# <a name="function-call-operator-"></a>Оператор вызова функции: ()

Вызов функции — это разновидность *`postfix-expression`* , сформированная выражением, определяющим функцию, за которой следует оператор вызова функции, **`()`** . Объект может объявить `operator ()` функцию, которая предоставляет семантику вызова функции для объекта.

## <a name="syntax"></a>Синтаксис

> *`postfix-expression`*:\
> &nbsp;&nbsp;&nbsp;&nbsp;*`postfix-expression`* **`(`** *`argument-expression-list`* <sub>opt</sub> **`)`**

## <a name="remarks"></a>Комментарии

Аргументы оператора вызова функции берутся из *`argument-expression-list`* , разделенного запятыми списка выражений. Значения этих выражений передаются в функцию в качестве аргументов. *Аргумент-expression-list* может быть пустым. До C++ 17 порядок вычисления выражения функции и выражений аргументов не определен и может возникать в любом порядке. В C++ 17 и более поздних версиях выражение функции вычисляется перед любыми выражениями аргументов или аргументами по умолчанию. Выражения аргументов вычисляются в неопределенной последовательности.

*`postfix-expression`* Определяет вызываемую функцию. Он должен быть равен адресу функции. Он может принимать любое из нескольких форм:

- имя или указатель функции или объекта функции;
- выражение lvalue, которое ссылается на функцию или объект функции,
- метод доступа к функции-члену, явный или подразумеваемый.

Функция, заданная параметром, *`postfix-expression`* может быть перегруженной функцией. Обычные правила для разрешения перегрузки определяют фактическую функцию для вызова.

Некоторые примеры объявлений:

- Функция, возвращающая тип `T`. Пример объявления:

    ```cpp
    T func( int i );
    ```

- Указатель на функцию, возвращающую тип `T`. Пример объявления:

    ```cpp
    T (*func)( int i );
    ```

- Ссылка на функцию, возвращающую тип `T`. Пример объявления:

    ```cpp
    T (&func)(int i);
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

Вызов функции вычисляет значение rvalue, если только функция не объявлена как ссылочный тип. Функции с возвращаемыми ссылочными типами оцениваются как значения lvalue. Эти функции можно использовать в левой части оператора присваивания, как показано ниже:

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

Приведенный выше код определяет класс с именем `Point` , который содержит закрытые объекты данных, представляющие координаты *x* и *y* . Эти объекты данных необходимо изменить, а значения — извлечь. Программа — это лишь одно из нескольких решений для такого класса. Также можно использовать функции `GetX` и `SetX` или `GetY` и `SetY`.

Функции, возвращающие типы классов, указатели на типы классов или ссылки на типы классов можно использовать как левый операнд в операторах выбора члена. Следующий код является допустимым:

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

## <a name="see-also"></a>См. также

[Постфиксные выражения](../cpp/postfix-expressions.md)<br/>
[Встроенные операторы, приоритет и ассоциативность C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Вызов функции](../c-language/function-call-c.md)
