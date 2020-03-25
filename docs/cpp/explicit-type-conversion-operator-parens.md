---
title: 'Оператор явного преобразования типа: ()'
ms.date: 11/04/2016
helpviewer_keywords:
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
ms.openlocfilehash: 079a3390df56ba55bd4d71a320faa249266abb54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189017"
---
# <a name="explicit-type-conversion-operator-"></a>Оператор явного преобразования типа: ()

В C++ разрешаются явные преобразования типов с использованием синтаксиса, аналогичного синтаксису вызова функции.

## <a name="syntax"></a>Синтаксис

```
simple-type-name ( expression-list )
```

## <a name="remarks"></a>Remarks

*Простое-Type-Name* , за которым следует *список выражений* , заключенный в круглые скобки, конструирует объект указанного типа с помощью указанных выражений. В следующем примере показано явное преобразование типа в тип int.

```cpp
int i = int( d );
```

В следующем примере показан класс `Point`.

## <a name="example"></a>Пример

```cpp
// expre_Explicit_Type_Conversion_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class Point
{
public:
    // Define default constructor.
    Point() { _x = _y = 0; }
    // Define another constructor.
    Point( int X, int Y ) { _x = X; _y = Y; }

    // Define "accessor" functions as
    // reference types.
    unsigned& x() { return _x; }
    unsigned& y() { return _y; }
    void Show()   { cout << "x = " << _x << ", "
                         << "y = " << _y << "\n"; }
private:
    unsigned _x;
    unsigned _y;
};

int main()
{
    Point Point1, Point2;

    // Assign Point1 the explicit conversion
    //  of ( 10, 10 ).
    Point1 = Point( 10, 10 );

    // Use x() as an l-value by assigning an explicit
    //  conversion of 20 to type unsigned.
    Point1.x() = unsigned( 20 );
    Point1.Show();

    // Assign Point2 the default Point object.
    Point2 = Point();
    Point2.Show();
}
```

## <a name="output"></a>Выходные данные

```Output
x = 20, y = 10
x = 0, y = 0
```

Хотя в предыдущем примере показано явное преобразование типов с помощью констант, тот же метод применим и для выполнения таких преобразований для объектов. Это демонстрируется в следующем фрагменте кода.

```cpp
int i = 7;
float d;

d = float( i );
```

Явные преобразования типов также можно задавать с помощью синтаксиса приведения. Предыдущий пример, перезаписанный с использованием синтаксиса приведения, выглядит следующим образом:

```cpp
d = (float)i;
```

Преобразования отдельных значений в стиле приведения и в стиле функции дают одинаковые результаты. Однако в синтаксисе стиля функции можно определить несколько аргументов для преобразования. Это различие имеет важное значение для пользовательских типов. Рассмотрим класс `Point` и его преобразования.

```cpp
struct Point
{
    Point( short x, short y ) { _x = x; _y = y; }
    ...
    short _x, _y;
};
...
Point pt = Point( 3, 10 );
```

В предыдущем примере, в котором используется преобразование в стиле функции, показано, как преобразовать два значения (один для *x* и один для *y*) в определяемый пользователем тип `Point`.

> [!CAUTION]
>  Явные преобразования типов следует использовать с осторожностью, поскольку они переопределяют встроенную проверку типов компилятора C++.

Нотация [приведения](../cpp/cast-operator-parens.md) должна использоваться для преобразований в типы, для которых не заданы простые типы с *именами* (например, указатели или ссылки). Преобразование в типы, которые могут быть выражены *простым-типом-именем* , может быть записано в любой форме.

Определение типа в приведениях недопустимо.

## <a name="see-also"></a>См. также раздел

[Постфиксные выражения](../cpp/postfix-expressions.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
