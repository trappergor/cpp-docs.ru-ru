---
title: Операторы &lt;list&gt;
ms.date: 11/04/2016
f1_keywords:
- list/std::operator!=
- list/std::operator&gt;
- list/std::operator&gt;=
- list/std::operator&lt;
- list/std::operator&lt;=
- list/std::operator==
ms.assetid: 8103d8f2-c30f-49ad-ac50-b3ba6a907ebe
helpviewer_keywords:
- std::operator!= (list)
- std::operator&gt; (list)
- std::operator&gt;= (list)
- std::operator&lt; (list)
- std::operator&lt;= (list)
- std::operator== (list)
ms.openlocfilehash: 919c24217866a57d0401c8cd6fea8f5cef02906b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537548"
---
# <a name="ltlistgt-operators"></a>Операторы &lt;list&gt;

||||
|-|-|-|
|[operator!=](#op_neq)|[оператор&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[оператор&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Проверяет неравенство объекта-списка слева от оператора объекту-списку справа от оператора.

```cpp
bool operator!=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Объект типа `list`.

*right*<br/>
Объект типа `list`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если списки не равны; в противном случае **false**.

### <a name="remarks"></a>Примечания

Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Два списка равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// list_op_ne.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
using namespace std;
list <int> c1, c2;
c1.push_back( 1 );
c2.push_back( 2 );

if ( c1 != c2 )
cout << "Lists not equal." << endl;
else
cout << "Lists equal." << endl;
}
/* Output:
Lists not equal.
*/
```

## <a name="op_lt"></a> operator&lt;

Проверяет, меньше ли объект-список слева от оператора, чем объект-список справа от оператора.

```cpp
bool operator<(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Объект типа `list`.

*right*<br/>
Объект типа `list`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список слева от оператора меньше, чем список справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Примечания

Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Отношение «меньше» между двумя объектами основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// list_op_lt.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 < c2 )
      cout << "List c1 is less than list c2." << endl;
   else
      cout << "List c1 is not less than list c2." << endl;
}
/* Output:
List c1 is less than list c2.
*/
```

## <a name="op_lt_eq"></a> operator&lt;=

Проверяет, что объект-список слева от оператора меньше или равен объекту-списку справа от оператора.

```cpp
bool operator<=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Объект типа `list`.

*right*<br/>
Объект типа `list`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список в левой части оператора меньше или равен списку в правой части оператора; в противном случае **false**.

### <a name="remarks"></a>Примечания

Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Отношение «меньше или равно» между двумя объектами основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// list_op_le.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 <= c2 )
      cout << "List c1 is less than or equal to list c2." << endl;
   else
      cout << "List c1 is greater than list c2." << endl;
}
/* Output:
List c1 is less than or equal to list c2.
*/
```

## <a name="op_eq_eq"></a> operator==

Проверяет, равен ли объект-список слева от оператора объекту-списку справа от оператора.

```cpp
bool operator==(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Объект типа `list`.

*right*<br/>
Объект типа `list`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список слева от оператора равен списку справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Примечания

Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Два списка равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// list_op_eq.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
int main( )
{
   using namespace std;

   list <int> c1, c2;
   c1.push_back( 1 );
   c2.push_back( 1 );

   if ( c1 == c2 )
      cout << "The lists are equal." << endl;
   else
      cout << "The lists are not equal." << endl;
}
/* Output:
The lists are equal.
*/
```

## <a name="op_gt"></a> operator&gt;

Проверяет, больше ли объект-список слева от оператора, чем объект-список справа от оператора.

```cpp
bool operator>(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Объект типа `list`.

*right*<br/>
Объект типа `list`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список слева от оператора больше списка справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Примечания

Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Отношение «больше» между двумя объектами основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// list_op_gt.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 > c2 )
      cout << "List c1 is greater than list c2." << endl;
   else
      cout << "List c1 is not greater than list c2." << endl;
}
/* Output:
List c1 is greater than list c2.
*/
```

## <a name="op_gt_eq"></a> operator&gt;=

Проверяет, что объект-список слева от оператора больше или равен объекту-списку справа от оператора.

```cpp
bool operator>=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Объект типа `list`.

*right*<br/>
Объект типа `list`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список слева от оператора больше или равен списку справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Примечания

Сравнение между объектами списков основывается на попарном сравнении элементов этих списков. Отношение «больше или равно» между двумя объектами основывается на сравнении первой пары неравных элементов.

### <a name="example"></a>Пример

```cpp
// list_op_ge.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 >= c2 )
      cout << "List c1 is greater than or equal to list c2." << endl;
   else
      cout << "List c1 is less than list c2." << endl;
}
/* Output:
List c1 is greater than or equal to list c2.
*/
```

## <a name="see-also"></a>См. также

[\<list>](../standard-library/list.md)<br/>
