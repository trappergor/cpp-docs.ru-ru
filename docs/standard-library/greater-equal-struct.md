---
title: "Структура greater_equal | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::greater_equal
dev_langs: C++
helpviewer_keywords:
- greater_equal struct
- greater_equal function
ms.assetid: a8ba911b-7af8-4653-b972-d8618f4df7d5
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6fbffd75fedd267f8034e919bedefd79a63838e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="greaterequal-struct"></a>Структура greater_equal
Бинарный предикат, который выполняет на своих аргументах операцию сравнения "больше или равно" ( `operator>=`).  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Type = void>
struct greater_equal : public binary_function <Type, Type, bool>  
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator>=
template <>
struct greater_equal<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left)>= std::forward<U>(Right));
 };
```  
  
#### <a name="parameters"></a>Параметры  
 `Type`, `T`, `U`  
 Любой тип, поддерживающий `operator>=`, принимающий операнды указанного или выводимого типа.  
  
 `Left`  
 Левый операнд в операции "больше или равно". Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue выводимого типа `T`.  
  
 `Right`  
 Правый операнд в операции "больше или равно". Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue выводимого типа `U`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат `Left >= Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator>=`.  
  
## <a name="remarks"></a>Примечания  
 Бинарный предикат `greater_equal`< `Type`> обеспечивает строгое слабое упорядочивание набора значений элементов типа `Type` в классы эквивалентности тогда и только тогда, когда этот тип удовлетворяет стандартным математическим требованиям для такого упорядочивания. Специализации для любого типа указателя дают общее упорядочение элементов в том, что все элементы из различных значений упорядочиваются относительно друг друга.  
  
## <a name="example"></a>Пример  
  
```cpp  
// functional_greater_equal.cpp  
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
   v1.push_back( 6262 );  
   v1.push_back( 6262 );  
   for ( i = 0 ; i < 5 ; i++ )  
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
   // specify binary predicate greater_equal<int>( )  
   sort( v1.begin( ), v1.end( ), greater_equal<int>( ) );  
   cout << "Resorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
## <a name="output"></a>Вывод  
  
```
Original vector v1 = (6262 6262 41 18467 6334 26500 19169)
Sorted vector v1 = (41 6262 6262 6334 18467 19169 26500)
Resorted vector v1 = (26500 19169 18467 6334 6262 6262 41)
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<functional>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)



