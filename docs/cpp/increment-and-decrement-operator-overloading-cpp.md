---
title: Перегрузка операторов увеличения и уменьшения (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators [C++]
- increment operators [C++], types of
- decrement operators [C++]
- decrement operators [C++], types of
ms.assetid: 5423c6ce-3999-4a77-92f6-ad540add1b1d
ms.openlocfilehash: 10cda57b74a7da57f2d48b91854b5d37c8d181f1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186988"
---
# <a name="increment-and-decrement-operator-overloading-c"></a>Перегрузка операторов увеличения и уменьшения (C++)

Операторы инкремента и декремента относятся к особой категории, поскольку имеется два варианта каждого из них:

- преинкрементный и постинкрементный операторы;

- предекрементный и постдекрементный операторы.

При написании функций перегруженных операторов полезно реализовать отдельные версии для префиксной и постфиксной форм этих операторов. Для различения этих двух правил наблюдается следующее правило: префиксная форма оператора объявляется точно так же, как любой другой унарный оператор. постфиксная форма принимает дополнительный аргумент типа **`int`** .

> [!NOTE]
> При указании перегруженного оператора для постфиксной формы оператора инкремента или декремента дополнительный аргумент должен иметь тип **`int`** ; при указании любого другого типа возникает ошибка.

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

Аргумент типа **`int`** , который обозначает постфиксную форму оператора инкремента или декремента, обычно не используется для передачи аргументов. Он обычно содержит значение 0. Однако его можно использовать следующим образом:

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

Для передачи этих значений с помощью операторов инкремента и декремента не существует иного синтаксиса, кроме явного вызова, как показано в предыдущем примере. Более простой способ реализации этой функции — перегрузить оператор сложения и присваивания ( **+=** ).

## <a name="see-also"></a>См. также раздел

[Перегрузка операторов](../cpp/operator-overloading.md)
