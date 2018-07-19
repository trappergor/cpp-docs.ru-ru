---
title: Структура iterator_traits | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::iterator_traits
dev_langs:
- C++
helpviewer_keywords:
- iterator_traits struct
- iterator_traits class
ms.assetid: 8b92c2c5-f658-402f-8ca1-e7ae301b8514
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0b4221e32b6e85df0b559b1d6d4ecda381d8e3d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959642"
---
# <a name="iteratortraits-struct"></a>Структура iterator_traits

Вспомогательная структура-шаблон, используется для указания всех критических определений типов, которые должен иметь итератор.

## <a name="syntax"></a>Синтаксис

```cpp
struct iterator_traits {
   typedef typename Iterator::iterator_category iterator_category;
   typedef typename Iterator::value_type value_type;
   typedef typename Iterator::difference_type difference_type;
   typedef difference_type distance_type;
   typedef typename Iterator::pointer pointer;
   typedef typename Iterator::reference reference;
   };
```

## <a name="remarks"></a>Примечания

Структура-шаблон определяет типы элементов

- `iterator_category`: синоним `Iterator::iterator_category`.

- `value_type`: синоним `Iterator::value_type`.

- `difference_type`: синоним `Iterator::difference_type`.

- `distance_type`: синоним `Iterator::difference_type.`

- `pointer`: синоним `Iterator::pointer`.

- `reference`: синоним `Iterator::reference`.

Частичные специализации определяют критические типы, связанные с указателем на объект типа **тип \***  или const **тип \***.

В этой реализации вы также можете применить несколько шаблонов функций, которые не используют частичную специализацию:

```cpp
template <class Category, class Type, class Diff>
C _Iter_cat(const iterator<Category, Ty, Diff>&);

template <class Ty>
random_access_iterator_tag _Iter_cat(const Ty *);

template <class Category, class Ty, class Diff>
Ty *val_type(const iterator<Category, Ty, Diff>&);

template <class Ty>
Ty *val_type(const Ty *);

template <class Category, class Ty, class Diff>
Diff *_Dist_type(const iterator<Category, Ty, Diff>&);

template <class Ty>
ptrdiff_t *_Dist_type(const Ty *);
```

что определяет некоторые из тех же типов более косвенно. Используйте эти функции как аргументы для вызова функции. Их единственная цель — предоставить полезный параметр шаблона класса в вызываемую функцию.

## <a name="example"></a>Пример

```cpp
// iterator_traits.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <vector>
#include <list>

using namespace std;

template< class it >
void
function( it i1, it i2 )
{
   iterator_traits<it>::iterator_category cat;
   cout << typeid( cat ).name( ) << endl;
   while ( i1 != i2 )
   {
      iterator_traits<it>::value_type x;
      x = *i1;
      cout << x << " ";
      i1++;
   };
   cout << endl;
};

int main( )
{
   vector<char> vc( 10,'a' );
   list<int> li( 10 );
   function( vc.begin( ), vc.end( ) );
   function( li.begin( ), li.end( ) );
}
\* Output:
struct std::random_access_iterator_tag
a a a a a a a a a a
struct std::bidirectional_iterator_tag
0 0 0 0 0 0 0 0 0 0
*\
```

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<iterator>](../standard-library/iterator.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
