---
title: "Структура iterator_traits | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::iterator_traits"
  - "xutility/std::iterator_traits"
  - "iterator_traits"
  - "std.iterator_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator_traits - класс"
  - "iterator_traits - структура"
ms.assetid: 8b92c2c5-f658-402f-8ca1-e7ae301b8514
caps.latest.revision: 19
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Структура iterator_traits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Структура вспомогательных шаблона, используемая для определения все критичные определения типов, которые итератор должен иметь.  
  
## Синтаксис  
  
```  
template<class Iterator>  
    struct iterator_traits {  
        typedef typename Iterator::iterator_category iterator_category;  
        typedef typename Iterator::value_type value_type;  
        typedef typename Iterator::difference_type difference_type;  
        typedef difference_type distance_type;  
        typedef typename Iterator::pointer pointer;  
        typedef typename Iterator::reference reference;  
    };  
template<class Type>  
    struct iterator_traits<Type*> {  
        typedef random_access_iterator_tag iterator_category;  
        typedef Type value_type;  
        typedef ptrdiff_t difference_type;  
        typedef difference_type distance_type;  
        typedef Type *pointer;  
        typedef Type& reference;  
    };  
template<class Type>  
    struct iterator_traits<const Type*> {  
        typedef random_access_iterator_tag iterator_category;  
        typedef Type value_type;  
        typedef ptrdiff_t difference_type;  
        typedef difference_type distance_type;  
        typedef const Type *pointer;  
        typedef const Type& reference;  
    };  
```  
  
## Заметки  
 Структура шаблона определяет типы члена  
  
-   **iterator\_category**: синоним для **Iterator::iterator\_category**.  
  
-   `value_type`: синоним для **Iterator::value\_type**.  
  
-   `difference_type`: синоним для **Iterator::difference\_type**.  
  
-   `distance_type`: синоним для **Iterator::difference\_type.**  
  
-   **указатель**: синоним для **Iterator::pointer**.  
  
-   **reference**: синоним для **Iterator::reference**.  
  
 Частично специализации определяют критические типы, связанные с указателем объекта типа const **Type \*** или **Type \***.  
  
 В этой реализации можно также использовать шаблонных несколько функций, которые не используют частично специализацию:  
  
```  
template<class Category, class Type, class Diff>  
C _Iter_cat(const iterator<Category, Ty, Diff>&);  
template<class Ty>  
    random_access_iterator_tag _Iter_cat(const Ty *);  
  
template<class Category, class Ty, class Diff>  
Ty *_Val_type(const iterator<Category, Ty, Diff>&);  
template<class Ty>  
    Ty *_Val_type(const Ty *);  
  
template<class Category, class Ty, class Diff>  
Diff *_Dist_type(const iterator<Category, Ty, Diff>&);  
template<class Ty>  
    ptrdiff_t *_Dist_type(const Ty *);  
```  
  
 чтобы задать несколько тех же типов более косвенно.  Используются эти функции в качестве аргументов в вызове функции.  Их единственным назначением предоставляет полезный параметр шаблона класса вызываемой функции.  
  
## Пример  
  
```  
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
```  
  
  **std::random\_access\_iterator\_tag структуры**  
**a**   
**std::bidirectional\_iterator\_tag структуры**  
**0 0 0 0 0 0 0 0 0 0**    
## Требования  
 **Заголовок:**\<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<iterator\>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)