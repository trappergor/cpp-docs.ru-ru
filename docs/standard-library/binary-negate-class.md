---
title: Класс binary_negate
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::binary_negate
helpviewer_keywords:
- binary_negate class
ms.assetid: 7b86f02c-af7e-4c7f-9df1-08addae4dd65
ms.openlocfilehash: a2aa5e2521eafbdd5ab7be93ad133f118a8d9356
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536648"
---
# <a name="binarynegate-class"></a>Класс binary_negate

Класс шаблона, предоставляющий функцию-член, которая инвертирует возвращаемое значение указанной бинарной функции.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Operation>
class binary_negate
    : public binaryFunction <typename Operation::first_argument_type,
                              typename Operation::second_argument_type, bool>
{
public:
    explicit binary_negate(const Operation& Func);
    bool operator()(const typename Operation::first_argument_type& left,
                    const typename Operation::second_argument_type& right) const;
};
```

### <a name="parameters"></a>Параметры

*Func*<br/>
Бинарная функция, которая должна быть инвертирована.

*left*<br/>
Левый операнд бинарной функции, которая должна быть инвертирована.

*right*<br/>
Правый операнд бинарной функции, которая должна быть инвертирована.

## <a name="return-value"></a>Возвращаемое значение

Отрицание бинарной функции.

## <a name="remarks"></a>Примечания

Этот класс шаблона сохраняет копию объекта бинарной функции _ *Func*. В нем определяется функция-член `operator()`, которая возвращает **!**\_ *Func(left, right).*

Конструктор `binary_negate` редко используется напрямую. Вспомогательная функция [not2](../standard-library/functional-functions.md#not2) обычно выбирается для объявления и использования предиката адаптера **binary_negator**.

## <a name="example"></a>Пример

```cpp
// functional_binary_negate.cpp
// compile with: /EHsc
#define _CRT_RAND_S
#include <stdlib.h>

#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   vector <unsigned int> v1;
   vector <unsigned int>::iterator Iter1;

   unsigned int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   unsigned int randVal = 0;
   for ( i = 0 ; i < 5 ; i++ )
   {
      rand_s(&randVal);
      v1.push_back( randVal );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<unsigned int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // use the binary_negate function
   sort( v1.begin( ), v1.end( ),
   binary_negate<less<unsigned int> >(less<unsigned int>( ) ) );

   // The helper function not2 could also have been used
   // in the above line and is usually preferred for convenience
   // sort( v1.begin( ), v1.end( ), not2(less<unsigned int>( ) ) );

   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
/* Output:
Original vector v1 = ( 6262 6262 2233879413 2621500314 580942933 3715465425 3739828298 )
Sorted vector v1 = ( 6262 6262 580942933 2233879413 2621500314 3715465425 3739828298 )
Resorted vector v1 = ( 3739828298 3715465425 2621500314 2233879413 580942933 6262 6262 )
*/
```

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
