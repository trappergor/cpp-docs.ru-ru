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
ms.openlocfilehash: 9dc9440db9ea1ff7285ff9b682f6be9900c2a1ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184317"
---
# <a name="explicit-type-conversion-operator-"></a>Оператор явного преобразования типа: ()

В C++ разрешаются явные преобразования типов с использованием синтаксиса, аналогичного синтаксису вызова функции.

## <a name="syntax"></a>Синтаксис

```
simple-type-name ( expression-list )
```

## <a name="remarks"></a>Примечания

Объект *простое имя типа* следуют *список выражений* заключено в круглые скобки конструкции объекта указанного типа, используя указанное выражение. В следующем примере показано явное преобразование типа в тип int.

```cpp
int i = int( d );
```

В следующем примере показан `Point` класса.

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

## <a name="output"></a>Вывод

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

Предыдущий пример, использующий функциональное преобразование, показано, как преобразовать два значения (одно для *x* и один для *y*) для определяемого пользователем типа `Point`.

> [!CAUTION]
>  Явные преобразования типов следует использовать с осторожностью, поскольку они переопределяют встроенную проверку типов компилятора C++.

[Приведения](../cpp/cast-operator-parens.md) notation должен использоваться для преобразования в типы, у которых нет *простое имя типа* (указатель или ссылка типами, например). Преобразование в типы, которые могут быть выражены с *простое имя типа* могут записываться в любой форме.

Определение типа в приведениях недопустимо.

## <a name="see-also"></a>См. также

[Постфиксные выражения](../cpp/postfix-expressions.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)