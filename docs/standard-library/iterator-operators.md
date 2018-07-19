---
title: Операторы &lt;iterator&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- xutility/std::operator!=
- xutility/std::operator&gt;
- xutility/std::operator&gt;=
- xutility/std::operator&lt;
- xutility/std::operator&lt;=
- xutility/std::operator+
- xutility/std::operator-
- xutility/std::operator==
dev_langs:
- C++
ms.assetid: b7c664f0-49d4-4993-b5d1-9ac4859fdddc
helpviewer_keywords:
- std::operator!= (iterator)
- std::operator&gt; (iterator)
- std::operator&gt;= (iterator)
- std::operator&lt; (iterator)
- std::operator&lt;= (iterator), std::operator== (iterator)
ms.openlocfilehash: e7dcd064216a9c1f1ba3f014b0f418b18b61193f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954699"
---
# <a name="ltiteratorgt-operators"></a>Операторы &lt;iterator&gt;

||||
|-|-|-|
|[оператор!=](#op_neq)|[оператор&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[оператор&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator+](#op_add)|
|[operator-](#operator-)|[оператор==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Проверяет объект итератора в левой части оператора на неравенство объекту итератора в правой части.

```cpp
template <class RandomIterator>
bool operator!=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);

template <class Type, class CharType, class Traits, class Distance>
bool operator!=(const istream_iterator<Type, CharType, Traits, Distance>& left, const istream_iterator<Type, CharType, Traits, Distance>& right);

template <class CharType, class Tr>
bool operator!=(const istreambuf_iterator<CharType, Traits>& left, const istreambuf_iterator<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*слева* объект типа `iterator`.

*правом* объект типа `iterator`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если итераторы не равны; **false**, если итераторы равны.

### <a name="remarks"></a>Примечания

Один итератор равен другому, если они адресуют одни и те же элементы в контейнере. Если два итератора указывают на различные элементы в контейнере, они не равны.

### <a name="example"></a>Пример

```cpp
// iterator_op_ne.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 9 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 != rVPOS2 )
      cout << "The iterators are not equal." << endl;
   else
      cout << "The iterators are equal." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 != rVPOS2 )
      cout << "The iterators are not equal." << endl;
   else
      cout << "The iterators are equal." << endl;
}
```

```Output
The vector vec is: ( 1 2 3 4 5 6 7 8 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 8.
The iterators are equal.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 7.
The iterators are not equal.
```

## <a name="op_eq_eq"></a> operator==

Проверяет объект итератора в левой части оператора на равенство объекту итератора в правой части.

```cpp
template <class RandomIterator1, class RandomIterator2>
bool operator==(
    const move_iterator<RandomIterator1>& left,
    const move_iterator<RandomIterator2>& right);

template <class RandomIterator1, class RandomIterator2>
bool operator==(
    const reverse_iterator<RandomIterator1>& left,
    const reverse_iterator<RandomIterator2>& right);

template <class Type, class CharType, class Traits, class Distance>
bool operator==(
    const istream_iterator<Type, CharType, Traits, Distance>& left,
    const istream_iterator<Type, CharType, Traits, Distance>& right);

template <class CharType, class Tr>
bool operator==(
    const istreambuf_iterator<CharType, Traits>& left,
    const istreambuf_iterator<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*слева* объект типа iterator.

*правом* объект типа iterator.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если итераторы равны; **false** Если итераторы не равны.

### <a name="remarks"></a>Примечания

Один итератор равен другому, если они адресуют одни и те же элементы в контейнере. Если два итератора указывают на различные элементы в контейнере, они не равны.

Первые два шаблона оператора возвращает значение true, только если оба *левой* и *правой* сохранить тот же итератор. Третий оператор шаблона возвращает значение true, только если оба *левой* и *правой* хранить один и тот же указатель потока. Четвертый оператор-шаблон возвращает ` left.equal ( right)`.

### <a name="example"></a>Пример

```cpp
// iterator_op_eq.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 == rVPOS2 )
      cout << "The iterators are equal." << endl;
   else
      cout << "The iterators are not equal." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 == rVPOS2 )
      cout << "The iterators are equal." << endl;
   else
      cout << "The iterators are not equal." << endl;
}
```

```Output
The vector vec is: ( 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
The iterators are equal.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 8.
The iterators are not equal.
```

## <a name="op_lt"></a> operator&lt;

Определяет, верно ли, что объект итератора в левой части оператора меньше объекта итератора в правой части.

```cpp
template <class RandomIterator>
bool operator<(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Параметры

*слева* объект типа `iterator`.

*правом* объект типа `iterator`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если итератор в левой части выражения меньше итератора в правой части; **false**, если он больше или равен итератору справа.

### <a name="remarks"></a>Примечания

Один итератор меньше, чем другой, если он адресует элемент, который находится в контейнере раньше, чем элемент, адресуемый другим сравниваемым итератором. Один итератор не меньше, чем другой, если он адресует либо тот же самый элемент, либо элемент, который находится в контейнере дальше, чем элемент, адресуемый другим сравниваемым итератором.

### <a name="example"></a>Пример

```cpp
// iterator_op_lt.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 0 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1& rVPOS2 initially point to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 < rVPOS2 )
      cout << "The iterator rVPOS1 is less than"
              << " the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is not less than"
              << " the iterator rVPOS2." << endl;

   rVPOS2++;
   cout << "The iterator rVPOS2 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 < rVPOS2 )
      cout << "The iterator rVPOS1 is less than"
              << " the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is not less than"
              << " the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1& rVPOS2 initially point to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 is not less than the iterator rVPOS2.
The iterator rVPOS2 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is less than the iterator rVPOS2.
```

## <a name="op_lt_eq"></a> operator&lt;=

Определяет, верно ли, что объект итератора в левой части оператора меньше или равен объекту итератора в правой части.

```cpp
template <class RandomIterator>
bool operator<=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Параметры

*слева* объект типа iterator.

*правом* объект типа iterator.

### <a name="return-value"></a>Возвращаемое значение

**true**, если итератор в левой части выражения меньше или равен итератору в правой части; **false**, если он больше итератора справа.

### <a name="remarks"></a>Примечания

Один итератор меньше или равен другому, если он адресует либо тот же самый элемент, либо элемент, который находится в контейнере раньше, чем элемент, адресуемый другим сравниваемым итератором. Один итератор больше, чем другой, если он адресует элемент, который находится в контейнере дальше, чем элемент, адресуемый другим сравниваемым итератором.

### <a name="example"></a>Пример

```cpp
// iterator_op_le.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ) + 1,
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the "
           << "second element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   cout << "The iterator rVPOS2 initially points to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 <= rVPOS2 )
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;

   rVPOS2++;
   cout << "The iterator rVPOS2 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 <= rVPOS2 )
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the second element
 in the reversed sequence: 8.
The iterator rVPOS2 initially points to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 is greater than the iterator rVPOS2.
The iterator rVPOS2 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is less than or equal to the iterator rVPOS2.
```

## <a name="op_gt"></a> operator&gt;

Определяет, верно ли, что объект итератора в левой части оператора больше объекта итератора в правой части.

```cpp
template <class RandomIterator>
bool operator>(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Параметры

*слева* объект типа iterator.

*правом* объект типа iterator.

### <a name="return-value"></a>Возвращаемое значение

**true**, если итератор в левой части выражения больше итератора в правой части; **false**, если он меньше или равен итератору справа.

### <a name="remarks"></a>Примечания

Один итератор больше, чем другой, если он адресует элемент, который находится в контейнере дальше, чем элемент, адресуемый другим сравниваемым итератором. Один итератор не больше, чем другой, если он адресует либо тот же самый элемент, либо элемент, который находится в контейнере раньше, чем элемент, адресуемый другим сравниваемым итератором.

### <a name="example"></a>Пример

```cpp
// iterator_op_gt.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1 & rVPOS2 initially point to "
           << "the first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 > rVPOS2 )
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 > rVPOS2 )
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1 & rVPOS2 initially point to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 is less than or equal to the iterator rVPOS2.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is greater than the iterator rVPOS2.
```

## <a name="op_gt_eq"></a> operator&gt;=

Определяет, верно ли, что объект итератора в левой части оператора больше или равен объекту итератора в правой части.

```cpp
template <class RandomIterator>
bool operator>=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Параметры

*слева* объект типа iterator.

*правом* объект типа iterator.

### <a name="return-value"></a>Возвращаемое значение

**true**, если итератор в левой части выражения больше или равен итератору в правой части; **false**, если он меньше итератора справа.

### <a name="remarks"></a>Примечания

Один итератор больше или равен другому, если он адресует либо тот же самый элемент, либо элемент, который находится в контейнере дальше, чем элемент, адресуемый другим сравниваемым итератором. Один итератор меньше, чем другой, если он адресует элемент, который находится в контейнере раньше, чем элемент, адресуемый другим сравниваемым итератором.

### <a name="example"></a>Пример

```cpp
// iterator_op_ge.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( ) + 1;

   cout << "The iterator rVPOS1 initially points to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   cout << "The iterator rVPOS2 initially points to the "
           << "second element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 >= rVPOS2 )
      cout << "The iterator rVPOS1 is greater than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than "
              << "the iterator rVPOS2." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 >= rVPOS2 )
      cout << "The iterator rVPOS1 is greater than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than "
              << "the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
The iterator rVPOS2 initially points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is less than the iterator rVPOS2.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is greater than or equal to the iterator rVPOS2.
```

## <a name="op_add"></a> operator+

Добавляет смещение к итератору и возвращает `move_iterator` или `reverse_iterator` с адресом вставленного элемента в новой позиции смещения.

```cpp
template <class RandomIterator, class Diff>
move_iterator<RandomIterator>
operator+(
    Diff _Off,
    const move_iterator<RandomIterator>& right);

template <class RandomIterator>
reverse_iterator<RandomIterator>
operator+(
    Diff _Off,
    const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Параметры

*_Off* количество позиций, const move_iterator или const reverse_iterator — смещение.

*правом* итератор для смещения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает сумму *правой* + *_Off*.

### <a name="example"></a>Пример

```cpp
// iterator_op_insert.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to "
           << "the first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   vector<int>::difference_type diff = 4;
   rVPOS1 = diff +rVPOS1;

   cout << "The iterator rVPOS1 now points to the fifth "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 now points to the fifth element
 in the reversed sequence: 2.
```

## <a name="operator-"></a>  оператор-

Вычитает один итератор из другого и возвращает разницу.

```cpp
template <class RandomIterator1, class RandomIterator2>
Tdiff operator-(
    const move_iterator<RandomIterator1>& left,
    const move_iterator<RandomIterator2>& right);

template <class RandomIterator1, class RandomIterator2>
Tdiff operator-(
    const reverse_iterator<RandomIterator1>& left,
    const reverse_iterator<RandomIterator2>& right);
```

### <a name="parameters"></a>Параметры

*слева* итератор.

*правом* итератор.

### <a name="return-value"></a>Возвращаемое значение

Разница между двумя итераторами `.`

### <a name="remarks"></a>Примечания

Первый оператор-шаблон возвращает `left.base() - right.base()`.

Второй оператор-шаблон возвращает `right.current - left.current`.

`Tdiff` определяется типом возвращенного выражения. В противном случае — `RandomIterator1::difference_type`.

### <a name="example"></a>Пример

```cpp
// iterator_op_sub.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
          rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1 & rVPOS2 initially point to "
        << "the first element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   for (i = 1; i < 5; ++i)
   {
      rVPOS2++;
   }
   cout << "The iterator rVPOS2 now points to the fifth "
        << "element\n in the reversed sequence: "
        << *rVPOS2 << "." << endl;

   vector<int>::difference_type diff = rVPOS2 - rVPOS1;
   cout << "The difference: rVPOS2 - rVPOS1= "
        << diff << "." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1 & rVPOS2 initially point to the first element
 in the reversed sequence: 10.
The iterator rVPOS2 now points to the fifth element
 in the reversed sequence: 2.
The difference: rVPOS2 - rVPOS1= 4.
```

## <a name="see-also"></a>См. также

[\<iterator>](../standard-library/iterator.md)<br/>
