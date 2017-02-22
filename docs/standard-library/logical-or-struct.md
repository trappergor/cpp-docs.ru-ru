---
title: "Структура logical_or | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.logical_or"
  - "std::logical_or"
  - "logical_or"
  - "xfunctional/std::logical_or"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_or - класс"
  - "logical_or - структура"
ms.assetid: ec8143f8-5755-4e7b-8025-507fb6bf6911
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Структура logical_or
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предопределенный объект функции, который выполняет логическую операцию рассеченности \(`operator||`\) на основе своих аргументов.  
  
## Синтаксис  
  
```  
template<class Type = void>  
   struct logical_or : public binary_function<Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator||  
template<>  
   struct logical_or<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            || std::forward<Type2>(Right));  
   };  
  
```  
  
#### Параметры  
 `Type`, `Type1`, `Type2`  
 Любой тип, поддерживающий `operator||`, принимающую операнды определение или возвращаемого типа.  
  
 `Left`  
 Левый операнд логические операции рассеченности.  Неспециализированный шаблон принимает аргумент ссылки значения типа `Type`.  Представляет шаблон повышает препровождение аргументов ссылки rvalue возвращаемого значения и типа `Type1`.  
  
 `Right`  
 Правый операнд логические операции рассеченности.  Неспециализированный шаблон принимает аргумент ссылки значения типа `Type`.  Представляет шаблон повышает препровождение аргументов ссылки rvalue возвращаемого значения и типа `Type2`.  
  
## Возвращаемое значение  
 Результат `Left``||``Right`.  Представляет шаблон повышает препровождение результата, который имеет тип, который возвращается `operator||`.  
  
## Заметки  
 Для пользовательских типов не допускающие сокращенные вычисления оценки операнда.  Оба аргумента вычисляются `operator||`.  
  
## Пример  
  
```  
// functional_logical_or.cpp  
// compile with: /EHsc  
#include <deque>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   deque <bool> d1, d2, d3( 7 );  
   deque <bool>::iterator iter1, iter2, iter3;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )  
   {  
      d1.push_back((bool)((rand() % 2) != 0));  
   }  
  
   int j;  
   for ( j = 0 ; j < 7 ; j++ )  
   {  
      d2.push_back((bool)((rand() % 2) != 0));  
   }  
  
   cout << boolalpha;    // boolalpha I/O flag on  
  
   cout << "Original deque:\n d1 = ( " ;  
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )  
      cout << *iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "Original deque:\n d2 = ( " ;  
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )  
      cout << *iter2 << " ";  
   cout << ")" << endl;  
  
   // To find element-wise disjunction of the truth values  
   // of d1 & d2, use the logical_or function object  
   transform( d1.begin( ), d1.end( ), d2.begin( ),  
      d3.begin( ), logical_or<bool>( ) );  
   cout << "The deque which is the disjuction of d1 & d2 is:\n d3 = ( " ;  
   for ( iter3 = d3.begin( ) ; iter3 != d3.end( ) ; iter3++ )  
      cout << *iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Исходный deque:**  
 **d1 \= true \(фактическое значение false значение false фактическое значение false значение false\)**  
**Исходный deque:**  
 **d2 \= false \(false значение false фактическое значение true фактическое значение true\)**  
**Deque, disjuction d1 & d2 выглядит следующим образом:**  
 **d3 \= true \(фактическое значение false фактическое значение true фактическое значение true\)**   
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)