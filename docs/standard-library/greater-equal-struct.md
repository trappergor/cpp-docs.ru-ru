---
title: "Структура greater_equal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.greater_equal"
  - "greater_equal"
  - "std::greater_equal"
  - "xfunctional/std::greater_equal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "greater_equal - структура"
  - "greater_equal - функция"
ms.assetid: a8ba911b-7af8-4653-b972-d8618f4df7d5
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Структура greater_equal
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Бинарный предикат, выполняет больш\-чем\-или\-равенство\- к операции \(`operator>=`\) на основе своих аргументов.  
  
## Синтаксис  
  
```  
template<class Type = void>  
   struct greater_equal : public binary_function <Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator>=  
template<>  
   struct greater_equal<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            >= std::forward<Type2>(Right));  
   };  
  
```  
  
#### Параметры  
 `Type`, `Type1`, `Type2`  
 Любой тип, поддерживающий `operator>=`, принимающую операнды определение или возвращаемого типа.  
  
 `Left`  
 Левый операнд больш\-чем\-или\-равенство\-к операции.  Неспециализированный шаблон принимает аргумент ссылки значения типа `Type`.  Представляет шаблон повышает препровождение аргументов ссылки rvalue возвращаемого значения и типа `Type1`.  
  
 `Right`  
 Правый операнд больш\-чем\-или\-равенство\-к операции.  Неспециализированный шаблон принимает аргумент ссылки значения типа `Type`.  Представляет шаблон повышает препровождение аргументов ссылки rvalue возвращаемого значения и типа `Type2`.  
  
## Возвращаемое значение  
 Результат `Left``>=``Right`.  Представляет шаблон повышает препровождение результата, который имеет тип, который возвращается `operator>=`.  
  
## Заметки  
 Бинарный предикат `greater_equal`\<`Type`\> предоставляет строгого слабое упорядочение набора значений элементов типа `Type` в классы эквивалентности, если и только в том случае, если этот тип удовлетворяют стандартные математические требования к таким образом, приказанным.  Специализацию для любого типа указателя создают полный упорядочение элементов, в котором все элементы сортируются в определенных значений относительно друг друга.  
  
## Пример  
  
```  
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
  
## Output  
  
```  
Original vector v1 = ( 6262 6262 41 18467 6334 26500 19169 )  
Sorted vector v1 = ( 41 6262 6262 6334 18467 19169 26500 )  
Resorted vector v1 = ( 26500 19169 18467 6334 6262 6262 41 )  
```  
  
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)