---
title: Класс raw_storage_iterator | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::reverse_iterator
- iterator/std::reverse_iterator::difference_type
- iterator/std::reverse_iterator::iterator_type
- iterator/std::reverse_iterator::pointer
- iterator/std::reverse_iterator::reference
- iterator/std::reverse_iterator::base
- iterator/std::reverse_iterator::operator_star
dev_langs:
- C++
helpviewer_keywords:
- std::reverse_iterator [C++]
- std::reverse_iterator [C++], difference_type
- std::reverse_iterator [C++], iterator_type
- std::reverse_iterator [C++], pointer
- std::reverse_iterator [C++], reference
- std::reverse_iterator [C++], base
- std::reverse_iterator [C++], operator_star
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 534d2755dfb38e739234dd15eb7f04263874c59e
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2018
ms.locfileid: "39209032"
---
# <a name="reverseiterator-class"></a>Класс reverse_iterator

Класс шаблона является адаптером итератора, описывающим объект обратного итератора, поведение которого аналогично поведению итератора произвольного доступа или двунаправленного итератора, но в обратном порядке. Он включает прохождение через диапазон в обратном порядке.

## <a name="syntax"></a>Синтаксис

```cpp
template <class RandomIterator>
class reverse_iterator
```

### <a name="parameters"></a>Параметры

RandomIterator тип, представляющий итератор для адаптации к применению в обратном порядке.

## <a name="remarks"></a>Примечания

Существующие контейнеры стандартной библиотеки C++ также задают типы `reverse_iterator` и `const_reverse_iterator` и обладают функциями-членами `rbegin` и `rend`, которые возвращают обратные итераторы. Эти итераторы обладают семантикой перезаписи. `reverse_iterator` Адаптера дополняет эти функции, поскольку они предоставляют семантику вставки и может использоваться с потоками.

`reverse_iterator` Требующее Двунаправленный итератор не должны обращаться члена функции `operator+=`, `operator+`, `operator-=`, `operator-`, или `operator[]`, который может использоваться только с итераторами произвольного доступа.

Диапазон итератора — [*первый*, *последнего*), где квадратная скобка слева обозначает Включение *первый* и круглая скобка справа — Включение всех элементов, но не включая *последнего* сам. Те же элементы включены в обращенной последовательности [ **rev** - *первый*, **rev** - *последнего*), Если *последнего* является элементом одной прошлом конца в последовательности, затем первый элемент **rev** - *первый* в обращенной последовательности указывает \*(*последнего* - 1). Идентификатор, который связывает все обратные итераторы с их базовыми итераторами:

&\*( **reverse_iterator** ( *я* )) == &\*( *я* - 1).

На практике это означает, что в обращенной последовательности reverse_iterator будет ссылаться на элемент, позиция которого на единицу превышает позицию элемента, на который итератор ссылается в исходной последовательности (т. е. находится справа от данного элемента). Поэтому если итератор обращался к элементу 6 в последовательности (2, 4, 6, 8), то итератор `reverse_iterator` будет обращаться к элементу 4 в обращенной последовательности (8, 6, 4, 2).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[reverse_iterator](#reverse_iterator)|Формирование итератора `reverse_iterator` по умолчанию или итератора `reverse_iterator` из базового итератора.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание:|
|-|-|
|[difference_type](#difference_type)|Тип, обеспечивающий разницу между двумя итераторами `reverse_iterator`, которые ссылаются на элементы в одном контейнере.|
|[iterator_type](#iterator_type)|Тип, предоставляющий базовый итератор для итератора `reverse_iterator`.|
|[pointer](#pointer)|Тип, содержащий указатель на элемент, к которому обращается итератор `reverse_iterator`.|
|[reference](#reference)|Тип, содержащий ссылку на элемент, к которому обращается итератор `reverse_iterator`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание:|
|-|-|
|[base](#base)|Восстановление базового итератора из соответствующего итератора `reverse_iterator`.|

### <a name="operators"></a>Операторы

|Оператор|Описание:|
|-|-|
|[operator_star](#op_star)|Возвращение элемента, к которому обращается `reverse_iterator`.|
|[operator+](#op_add)|Добавление смещения к итератору и возврат нового итератора `reverse_iterator`, который обращается к вставленному элементу в новой позиции смещения.|
|[оператор++](#op_add_add)|Увеличение `reverse_iterator` до следующего элемента.|
|[оператор+=](#op_add_eq)|Добавление заданного смещения из итератора `reverse_iterator`.|
|[operator-](#operator-)|Вычитание смещения из итератора `reverse_iterator` с возвратом итератора `reverse_iterator`, который обращается к элементу в позиции со сдвигом.|
|[оператор--](#operator--)|Уменьшение `reverse_iterator` до предыдущего элемента.|
|[оператор-=](#operator-_eq)|Вычитание заданного смещения из итератора `reverse_iterator`.|
|[оператор>](#operator-_gt)|Возвращение указателя на элемент, к которому обращается `reverse_iterator`.|
|[оператор[]](#op_at)|Возврат ссылки на смещение элемента из элемента, к которому обращается `reverse_iterator`, на указанное число позиций.|

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="base"></a>  reverse_iterator::base

Восстановление базового итератора из соответствующего итератора `reverse_iterator`.

```cpp
RandomIterator base() const;
```

### <a name="return-value"></a>Возвращаемое значение

Базовый интегратор `reverse_iterator`.

### <a name="remarks"></a>Примечания

Идентификатор, который связывает все обратные итераторы с их базовыми итераторами:

&\*( `reverse_iterator` ( *я* )) == &\*( *я* - 1).

На практике это означает, что в обращенной последовательности `reverse_iterator` будет ссылаться на элемент, позиция которого на единицу превышает позицию элемента, на который итератор ссылается в исходной последовательности (т. е. находится справа от данного элемента). Поэтому если итератор обращался к элементу 6 в последовательности (2, 4, 6, 8), то итератор `reverse_iterator` будет обращаться к элементу 4 в обращенной последовательности (8, 6, 4, 2).

### <a name="example"></a>Пример

```cpp
// reverse_iterator_base.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
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
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   vector <int>::iterator pos, bpos;
   pos = find ( vec.begin ( ), vec.end ( ), 6 );
   cout << "The iterator pos points to: " << *pos << "." << endl;

   typedef reverse_iterator<vector<int>::iterator>::iterator_type it_vec_int_type;

   reverse_iterator<it_vec_int_type> rpos ( pos );
   cout << "The reverse_iterator rpos points to: " << *rpos
        << "." << endl;

   bpos = rpos.base ( );
   cout << "The iterator underlying rpos is bpos & it points to: "
        << *bpos << "." << endl;
}
```

## <a name="difference_type"></a>  reverse_iterator::difference_type

Тип, обеспечивающий разницу между двумя итераторами `reverse_iterator`, которые ссылаются на элементы в одном контейнере.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type  difference_type;
```

### <a name="remarks"></a>Примечания

Тип отличия `reverse_iterator` совпадает с типом отличия итератора.

Этот тип является синонимом имени типа для признака итератора `iterator_traits`\< **RandomIterator**> **::pointer**.

### <a name="example"></a>Пример

См. пример объявления и использования `difference_type` в разделе [reverse_iterator::operator&#91;&#93;](#op_at).

## <a name="iterator_type"></a>  reverse_iterator::iterator_type

Тип, предоставляющий базовый итератор для итератора `reverse_iterator`.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Iterator`.

### <a name="example"></a>Пример

См. пример объявления и использования `iterator_type` в разделе [reverse_iterator::base](#base).

## <a name="op_star"></a>  reverse_iterator::operator\*

Возвращает элемент, к которому обращается reverse_iterator.

```cpp
reference operator*() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение элементов к которым обращается reverse_iterator.

### <a name="remarks"></a>Примечания

Оператор возвращает \*( **текущей** - 1).

### <a name="example"></a>Пример

```cpp
// reverse_iterator_op_ref.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   vector <int>::iterator pos, bpos;
   pos = find ( vec.begin ( ), vec.end ( ), 6 );

   // Declare a difference type for a parameter
   // declare a reference return type
   reverse_iterator<vector<int>::iterator>::reference refpos = *pos;
   cout << "The iterator pos points to: " << refpos << "." << endl;
}
```

## <a name="op_add"></a>  reverse_iterator::operator+

Добавление смещения к итератору и возврат нового итератора `reverse_iterator`, который обращается к вставленному элементу в новой позиции смещения.

```cpp
reverse_iterator<RandomIterator> operator+(difference_type Off) const;
```

### <a name="parameters"></a>Параметры

*Отключение* смещение для добавления реверсивный итератор.

### <a name="return-value"></a>Возвращаемое значение

Объект `reverse_iterator`, который обращается к элементу смещения.

### <a name="remarks"></a>Примечания

Эта функция-член может использоваться, только если `reverse_iterator` удовлетворяет требованиям для итератора произвольного доступа.

### <a name="example"></a>Пример

```cpp
// reverse_iterator_op_add.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the first element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   vector <int>::reverse_iterator rVPOS2 =rVPOS1 + 2; // offset added
   cout << "After the +2 offset, the iterator rVPOS2 points\n"
        << " to the 3rd element in the reversed sequence: "
        << *rVPOS2 << "." << endl;
}
```

```Output
The vector vec is: ( 2 4 6 8 10 ).
The vector vec reversed is: ( 10 8 6 4 2 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
After the +2 offset, the iterator rVPOS2 points
 to the 3rd element in the reversed sequence: 6.
```

## <a name="op_add_add"></a>  reverse_iterator::operator++

Увеличивает reverse_iterator до предыдущего элемента.

```cpp
reverse_iterator<RandomIterator>& operator++();
reverse_iterator<RandomIterator> operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает предварительно увеличенный `reverse_iterator`, а второй, постинкрементный оператор, возвращает копию увеличенного `reverse_iterator`.

### <a name="remarks"></a>Примечания

Эта функция-член может использоваться, только если `reverse_iterator` удовлетворяет требованиям для двустороннего итератора.

### <a name="example"></a>Пример

```cpp
// reverse_iterator_op_incr.cpp
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
      vec.push_back ( 2 * i - 1 );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   rVPOS1++;  // postincrement, preincrement: ++rVPSO1

   cout << "After incrementing, the iterator rVPOS1 points\n"
        << " to the second element in the reversed sequence: "
        << *rVPOS1 << "." << endl;
}
```

```Output
The vector vec is: ( 1 3 5 7 9 ).
The vector vec reversed is: ( 9 7 5 3 1 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 9.
After incrementing, the iterator rVPOS1 points
 to the second element in the reversed sequence: 7.
```

## <a name="op_add_eq"></a>  reverse_iterator::operator+=

Добавляет заданное смещение из reverse_iterator.

```cpp
reverse_iterator<RandomIterator>& operator+=(difference_type Off);
```

### <a name="parameters"></a>Параметры

*Отключение* смещение, на который необходимо увеличить итератор.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент, к которому обращается `reverse_iterator`.

### <a name="example"></a>Пример

```cpp
// reverse_iterator_op_addoff.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   rVPOS1+=2;   // addition of an offset
   cout << "After the +2 offset, the iterator rVPOS1 now points\n"
        << " to the third element in the reversed sequence: "
        << *rVPOS1 << "." << endl;
}
```

```Output
The vector vec is: ( 2 4 6 8 10 ).
The vector vec reversed is: ( 10 8 6 4 2 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
After the +2 offset, the iterator rVPOS1 now points
 to the third element in the reversed sequence: 6.
```

## <a name="reverse_iterator__operator-"></a>  reverse_iterator::operator-

Вычитание смещения из итератора `reverse_iterator` с возвратом итератора `reverse_iterator`, который обращается к элементу в позиции со сдвигом.

```cpp
reverse_iterator<RandomIterator> operator-(difference_type Off) const;
```

### <a name="parameters"></a>Параметры

*Отключение* смещение, которое необходимо вычесть из reverse_iterator.

### <a name="return-value"></a>Возвращаемое значение

Объект `reverse_iterator`, который обращается к элементу смещения.

### <a name="remarks"></a>Примечания

Эта функция-член может использоваться, только если `reverse_iterator` удовлетворяет требованиям для итератора произвольного доступа.

### <a name="example"></a>Пример

```cpp
// reverse_iterator_op_sub.cpp
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
      vec.push_back ( 3 * i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the first element
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;

   cout << "The iterator rVPOS1 initially points to the last "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   vector <int>::reverse_iterator rVPOS2 =rVPOS1 - 2; // offset subtracted
   cout << "After the -2 offset, the iterator rVPOS2 points\n"
        << " to the 2nd element from the last in the reversed sequence: "
        << *rVPOS2 << "." << endl;
}
```

```Output
The vector vec is: ( 3 6 9 12 15 ).
The vector vec reversed is: ( 15 12 9 6 3 ).
The iterator rVPOS1 initially points to the last element
 in the reversed sequence: 3.
After the -2 offset, the iterator rVPOS2 points
 to the 2nd element from the last in the reversed sequence: 9.
```

## <a name="reverse_iterator__operator--"></a>  reverse_iterator::operator--

Уменьшает reverse_iterator до предыдущего элемента.

```cpp
reverse_iterator<RandomIterator>& operator--();
reverse_iterator<RandomIterator> operator--(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает предварительно уменьшенный `reverse_iterator`, а второй, постдекрементный оператор, возвращает копию уменьшенного `reverse_iterator`.

### <a name="remarks"></a>Примечания

Эта функция-член может использоваться, только если `reverse_iterator` удовлетворяет требованиям для двустороннего итератора.

### <a name="example"></a>Пример

```cpp
// reverse_iterator_op_decr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i - 1 );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the first element
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;

   cout << "The iterator rVPOS1 initially points to the last "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;
   rVPOS1--;  // postdecrement, predecrement: --rVPSO1

   cout << "After the decrement, the iterator rVPOS1 points\n"
        << " to the next-to-last element in the reversed sequence: "
        << *rVPOS1 << "." << endl;
}
```

```Output
The vector vec is: ( 1 3 5 7 9 ).
The vector vec reversed is: ( 9 7 5 3 1 ).
The iterator rVPOS1 initially points to the last element
 in the reversed sequence: 1.
After the decrement, the iterator rVPOS1 points
 to the next-to-last element in the reversed sequence: 3.
```

## <a name="reverse_iterator__operator-_eq"></a>  reverse_iterator::operator-=

Вычитание заданного смещения из итератора `reverse_iterator`.

```cpp
reverse_iterator<RandomIterator>& operator-=(difference_type Off);
```

### <a name="parameters"></a>Параметры

*Отключение* смещение, которое необходимо вычесть из `reverse_iterator`.

### <a name="remarks"></a>Примечания

Эта функция-член может использоваться, только если `reverse_iterator` удовлетворяет требованиям для итератора произвольного доступа.

Оператор вычисляет **current** + _ *Off*. и возвращает **\*this**.

### <a name="example"></a>Пример

```cpp
// reverse_iterator_op_suboff.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 3 * i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the first element
   vector <int>::reverse_iterator rVPOS1 = vec.rend ( ) - 1;

   cout << "The iterator rVPOS1 initially points to the last "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   rVPOS1-=2;      // Subtraction of an offset
   cout << "After the -2 offset, the iterator rVPOS1 now points\n"
        << " to the 2nd element from the last in the reversed sequence: "
        << *rVPOS1 << "." << endl;
}
```

```Output
The vector vec is: ( 3 6 9 12 15 ).
The vector vec reversed is: ( 15 12 9 6 3 ).
The iterator rVPOS1 initially points to the last element
 in the reversed sequence: 3.
After the -2 offset, the iterator rVPOS1 now points
 to the 2nd element from the last in the reversed sequence: 9.
```

## <a name="op_arrow"></a>  reverse_iterator::operator-&gt;

Возвращение указателя на элемент, к которому обращается `reverse_iterator`.

```cpp
pointer operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент, к которому обращается `reverse_iterator`.

### <a name="remarks"></a>Примечания

Оператор возвращает **&\*\*this**.

### <a name="example"></a>Пример

```cpp
// reverse_iterator_ptrto.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <utility>
#include <iostream>

int main( )
{
   using namespace std;

   typedef vector<pair<int,int> > pVector;
   pVector vec;
   vec.push_back(pVector::value_type(1,2));
   vec.push_back(pVector::value_type(3,4));
   vec.push_back(pVector::value_type(5,6));

   pVector::iterator pvIter;
   cout << "The vector vec of integer pairs is:\n( ";
   for ( pvIter = vec.begin ( ) ; pvIter != vec.end ( ); pvIter++)
      cout << "( " << pvIter -> first << ", " << pvIter -> second << ") ";
   cout << ")" << endl << endl;

   pVector::reverse_iterator rpvIter;
   cout << "The vector vec reversed is:\n( ";
   for ( rpvIter = vec.rbegin( ) ; rpvIter != vec.rend( ); rpvIter++ )
      cout << "( " << rpvIter -> first << ", " << rpvIter -> second << ") ";
   cout << ")" << endl << endl;

   pVector::iterator pos = vec.begin ( );
   pos++;
   cout << "The iterator pos points to:\n( " << pos -> first << ", "
   << pos -> second << " )" << endl << endl;

   pVector::reverse_iterator rpos (pos);

   // Use operator -> with return type: why type int and not int*
   int fint = rpos -> first;
   int sint = rpos -> second;

   cout << "The reverse_iterator rpos points to:\n( " << fint << ", "
   << sint << " )" << endl;
}
```

```Output
The vector vec of integer pairs is:
( ( 1, 2) ( 3, 4) ( 5, 6) )

The vector vec reversed is:
( ( 5, 6) ( 3, 4) ( 1, 2) )

The iterator pos points to:
( 3, 4 )

The reverse_iterator rpos points to:
( 1, 2 )
```

## <a name="op_at"></a>  reverse_iterator::operator[]

Возврат ссылки на смещение элемента из элемента, к которому обращается `reverse_iterator`, на указанное число позиций.

```cpp
reference operator[](difference_type Off) const;
```

### <a name="parameters"></a>Параметры

*Отключение* смещение от `reverse_iterator` адрес.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на смещение элемента.

### <a name="remarks"></a>Примечания

Оператор возвращает **\***( **\*this** + `Off`).

### <a name="example"></a>Пример

```cpp
// reverse_iterator_ret_ref.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   vector <int>::iterator pos;
   pos = find ( vec.begin ( ), vec.end ( ), 8 );
   reverse_iterator<vector<int>::iterator> rpos ( pos );

   // Declare a difference type for a parameter
   reverse_iterator<vector<int>::iterator>::difference_type diff = 2;

   cout << "The iterator pos points to: " << *pos << "." << endl;
   cout << "The iterator rpos points to: " << *rpos << "." << endl;

   // Declare a reference return type & use operator[]
   reverse_iterator<vector<int>::iterator>::reference refrpos = rpos [diff];
   cout << "The iterator rpos now points to: " << refrpos << "." << endl;
}
```

```Output
The vector vec is: ( 2 4 6 8 10 ).
The vector vec reversed is: ( 10 8 6 4 2 ).
The iterator pos points to: 8.
The iterator rpos points to: 6.
The iterator rpos now points to: 2.
```

## <a name="pointer"></a>  reverse_iterator::pointer

Тип, содержащий указатель на элемент, к которому обращается итератор `reverse_iterator`.

```cpp
typedef typename iterator_traits<RandomIterator>::pointer pointer;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом имени типа для признака итератора `iterator_traits`\< *RandomIterator*> **::pointer**.

### <a name="example"></a>Пример

```cpp
// reverse_iterator_pointer.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <utility>
#include <iostream>

int main( )
{
   using namespace std;

   typedef vector<pair<int,int> > pVector;
   pVector vec;
   vec.push_back( pVector::value_type( 1,2 ) );
   vec.push_back( pVector::value_type( 3,4 ) );
   vec.push_back( pVector::value_type( 5,6 ) );

   pVector::iterator pvIter;
   cout << "The vector vec of integer pairs is:\n" << "( ";
   for ( pvIter = vec.begin ( ) ; pvIter != vec.end ( ); pvIter++)
      cout << "( " << pvIter -> first << ", " << pvIter -> second << ") ";
   cout << ")" << endl;

   pVector::reverse_iterator rpvIter;
   cout << "\nThe vector vec reversed is:\n" << "( ";
   for ( rpvIter = vec.rbegin( ) ; rpvIter != vec.rend( ); rpvIter++)
      cout << "( " << rpvIter -> first << ", " << rpvIter -> second << ") ";
   cout << ")" << endl;

   pVector::iterator pos = vec.begin ( );
   pos++;
   cout << "\nThe iterator pos points to:\n"
        << "( " << pos -> first << ", "
        << pos -> second << " )" << endl;

   pVector::reverse_iterator rpos (pos);
   cout << "\nThe iterator rpos points to:\n"
        << "( " << rpos -> first << ", "
        << rpos -> second << " )" << endl;
}
```

```Output
The vector vec of integer pairs is:
( ( 1, 2) ( 3, 4) ( 5, 6) )

The vector vec reversed is:
( ( 5, 6) ( 3, 4) ( 1, 2) )

The iterator pos points to:
( 3, 4 )

The iterator rpos points to:
( 1, 2 )
```

## <a name="reference"></a>  reverse_iterator::reference

Тип, предоставляющий ссылку на элемент, к которому обращается reverse_iterator.

```cpp
typedef typename iterator_traits<RandomIterator>::reference reference;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом имени типа для признака итератора `iterator_traits`\< *RandomIterator*> **::reference**.

### <a name="example"></a>Пример

См. в разделе [reverse_iterator::operator&#91; &#93; ](#op_at) или [reverse_iterator::operator *](#op_star) примеры объявления и использования `reference`.

## <a name="reverse_iterator"></a>  reverse_iterator::reverse_iterator

Формирование итератора `reverse_iterator` по умолчанию или итератора `reverse_iterator` из базового итератора.

```cpp
reverse_iterator();
explicit reverse_iterator(RandomIterator right);

template <class Type>
reverse_iterator(const reverse_iterator<Type>& right);
```

### <a name="parameters"></a>Параметры

*правом* итератор, который необходимо адаптировать к `reverse_iterator`.

### <a name="return-value"></a>Возвращаемое значение

`reverse_iterator` по умолчанию или `reverse_iterator`, адаптирующий базовый итератор.

### <a name="remarks"></a>Примечания

Идентификатор, который связывает все обратные итераторы с их базовыми итераторами:

&\*( `reverse_iterator` ( *я* )) == &\*( *я* - 1).

На практике это означает, что в обращенной последовательности reverse_iterator будет ссылаться на элемент, позиция которого на единицу превышает позицию элемента, на который итератор ссылается в исходной последовательности (т. е. находится справа от данного элемента). Поэтому если итератор обращался к элементу 6 в последовательности (2, 4, 6, 8), то итератор `reverse_iterator` будет обращаться к элементу 4 в обращенной последовательности (8, 6, 4, 2).

### <a name="example"></a>Пример

```cpp
// reverse_iterator_reverse_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <algorithm>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;
   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rvIter;
   cout << "The vector vec reversed is: ( ";
   for ( rvIter = vec.rbegin( ) ; rvIter != vec.rend( ); rvIter++)
      cout << *rvIter << " ";
   cout << ")." << endl;

   vector <int>::iterator pos;
   pos = find ( vec.begin ( ), vec.end ( ), 4 );
   cout << "The iterator pos = " << *pos << "." << endl;

   vector <int>::reverse_iterator rpos ( pos );
   cout << "The reverse_iterator rpos = " << *rpos
        << "." << endl;
}
```

## <a name="see-also"></a>См. также

[\<iterator>](../standard-library/iterator.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
