---
title: Перегрузка операторов увеличения и уменьшения (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
ms.openlocfilehash: 40ae12130fdced9fd958c3b8316fa3b718ca9b5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374120"
---
# <a name="increment-and-decrement-operator-overloading-c"></a>Перегрузка операторов увеличения и уменьшения (C++)

Операторы инкремента и декремента относятся к особой категории, поскольку имеется два варианта каждого из них:

- преинкрементный и постинкрементный операторы;

- предекрементный и постдекрементный операторы.

При написании функций перегруженных операторов полезно реализовать отдельные версии для префиксной и постфиксной форм этих операторов. Чтобы различать эти два, соблюдается следующее правило: форма префикса оператора объявляется точно так же, как и любой другой неамортный оператор; postfix форма принимает дополнительный аргумент типа **Int**.

> [!NOTE]
> При указании перегруженного оператора для формы postfix оператора приращения или decrement дополнительный аргумент должен быть типа **Int;** указание любого другого типа генерирует ошибку.

В следующем примере показано определение операторов префиксных и постфиксных инкремента и декремента для класса `Point`.

```cpp
// increment_and_decrement1.cpp
class Point
{
public:
   // Declare prefix and postfix increment operators.
   Point& operator++();       // Prefix increment operator.
   Point operator++(int);     // Postfix increment operator.

   // Declare prefix and postfix decrement operators.
   Point& operator--();       // Prefix decrement operator.
   Point operator--(int);     // Postfix decrement operator.

   // Define default constructor.
   Point() { _x = _y = 0; }

   // Define accessor functions.
   int x() { return _x; }
   int y() { return _y; }
private:
   int _x, _y;
};

// Define prefix increment operator.
Point& Point::operator++()
{
   _x++;
   _y++;
   return *this;
}

// Define postfix increment operator.
Point Point::operator++(int)
{
   Point temp = *this;
   ++*this;
   return temp;
}

// Define prefix decrement operator.
Point& Point::operator--()
{
   _x--;
   _y--;
   return *this;
}

// Define postfix decrement operator.
Point Point::operator--(int)
{
   Point temp = *this;
   --*this;
   return temp;
}
int main()
{
}
```

Те же операторы можно определить в области видимости файла (глобально) с помощью следующих заголовков функций:

```cpp
friend Point& operator++( Point& )      // Prefix increment
friend Point& operator++( Point&, int ) // Postfix increment
friend Point& operator--( Point& )      // Prefix decrement
friend Point& operator--( Point&, int ) // Postfix decrement
```

Аргумент типа **int,** который обозначает форму postfix оператора приращения или decrement, обычно не используется для передачи аргументов. Он обычно содержит значение 0. Однако его можно использовать следующим образом:

```cpp
// increment_and_decrement2.cpp
class Int
{
public:
    Int &operator++( int n );
private:
    int _i;
};

Int& Int::operator++( int n )
{
    if( n != 0 )    // Handle case where an argument is passed.
        _i += n;
    else
        _i++;       // Handle case where no argument is passed.
    return *this;
}
int main()
{
   Int i;
   i.operator++( 25 ); // Increment by 25.
}
```

Для передачи этих значений с помощью операторов инкремента и декремента не существует иного синтаксиса, кроме явного вызова, как показано в предыдущем примере. Более простой способ реализации этой функциональности заключается в**+=** перегрузке оператора добавления/назначения ().

## <a name="see-also"></a>См. также раздел

[Перегрузка оператора](../cpp/operator-overloading.md)
