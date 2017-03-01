---
title: "Структура greater | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- greater
- xfunctional/std::greater
- std.greater
- std::greater
dev_langs:
- C++
helpviewer_keywords:
- greater struct
- greater function
ms.assetid: ebc348e1-edcd-466b-b21a-db95bd8f9079
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: bcb6c83709d8e0effc202ecfb13659e7f725b1d1
ms.lasthandoff: 02/24/2017

---
# <a name="greater-struct"></a>Структура greater
Бинарный предикат, который выполняет на своих аргументах операцию сравнения "больше чем" (`operator>`).  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Type = void>
struct greater : public binary_function <Type, Type, bool>  
{
    bool operator()(
    const Type& Left,
    const Type& Right) const;

 };

// specialized transparent functor for operator>
template <>
struct greater<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const
    ->  decltype(std::forward<T>(Left)> std::forward<U>(Right));
 };
```  
  
#### <a name="parameters"></a>Параметры  
 `Type`, `T`, `U`  
 Любой тип, поддерживающий `operator>`, принимающий операнды указанного или выводимого типа.  
  
 `Left`  
 Левый операнд в операции "больше чем". Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue выводимого типа `T`.  
  
 `Right`  
 Правый операнд в операции "больше чем". Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue выводимого типа `U`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат `Left``>``Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator>`.  
  
## <a name="remarks"></a>Примечания  
 Бинарный предикат `greater`< `Type`> обеспечивает строгое слабое упорядочивание набора значений элементов типа `Type` в классы эквивалентности тогда и только тогда, когда этот тип удовлетворяет стандартным математическим требованиям для такого упорядочивания. Специализации для любого типа указателя дают общее упорядочение элементов в том, что все элементы из различных значений упорядочиваются относительно друг друга.  
  
## <a name="example"></a>Пример  
  
```cpp  
// functional_greater.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <cstdlib>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator Iter1;  
  
   int i;  
   for ( i = 0 ; i < 8 ; i++ )  
   {  
      v1.push_back( rand( ) );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use default binary predicate less<int>( )  
   sort( v1.begin( ), v1.end( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in descending order,   
   // specify binary predicate greater<int>( )  
   sort( v1.begin( ), v1.end( ), greater<int>( ) );  
   cout << "Resorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
## <a name="output"></a>Вывод  
  
```
Original vector v1 = (41 18467 6334 26500 19169 15724 11478 29358)
Sorted vector v1 = (41 6334 11478 15724 18467 19169 26500 29358)
Resorted vector v1 = (29358 26500 19169 18467 15724 11478 6334 41)
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<functional>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




