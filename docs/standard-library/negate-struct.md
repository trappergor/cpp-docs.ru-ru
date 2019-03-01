---
title: negate - структура
ms.date: 11/04/2016
f1_keywords:
- functional/std::negate
helpviewer_keywords:
- negate struct
- negate class
ms.assetid: 8a372686-786e-4262-b37c-ca13dc11e62f
ms.openlocfilehash: d865577ed7052937b9fa2c2c1023b3a4befcb776
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006621"
---
# <a name="negate-struct"></a>negate - структура

Стандартный объект функции, который выполняет над своим аргументом арифметическую операцию замены знака (унарное `operator-`).

## <a name="syntax"></a>Синтаксис

```
template <class Type = void>
struct negate : public unary_function<Type, Type>
{
    Type operator()(const Type& Left) const;
};

// specialized transparent functor for unary operator-
template <>
struct negate<void>
{
  template <class Type>
  auto operator()(Type&& Left) const`
    -> decltype(-std::forward<Type>(Left));
};
```

### <a name="parameters"></a>Параметры

*Type*<br/>
Любой тип, поддерживающий `operator-`, принимающий операнды указанного или выводимого типа.

*Слева*<br/>
Операнд для замены знака. Специализированный шаблон выполняет точную пересылку lvalue и rvalue ссылочных аргументов выводимого типа *тип*.

## <a name="return-value"></a>Возвращаемое значение

Результат `-Left.`. Специализированный шаблон выполняет точную пересылку результата, который имеет тип, возвращаемый унарным `operator-`.

## <a name="example"></a>Пример

```cpp
// functional_negate.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <int> v1, v2 ( 8 );
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = -2 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // Finding the element-wise negatives of the vector v1
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), negate<int>( ) );

   cout << "The negated elements of the vector = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;
}
/* Output:
The vector v1 = ( -10 -5 0 5 10 15 20 25 )
The negated elements of the vector = ( 10 5 0 -5 -10 -15 -20 -25 )
*/
```

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
