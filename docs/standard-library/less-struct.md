---
title: "Структура less | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::less"
  - "std.less"
  - "less"
  - "xfunctional/std::less"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "less - структура"
  - "less - функция"
ms.assetid: 39349da3-11cd-4774-b2cc-b46af5aae5d7
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# Структура less
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Бинарный предикат, выполняет менее чем операция \(`operator<`\) на основе своих аргументов.  
  
## Синтаксис  
  
```  
template<class Type = void>  
   struct less : public binary_function <Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator<  
template<>  
   struct less<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            < std::forward<Type2>(Right));  
   };  
  
```  
  
#### Параметры  
 `Type`, `Type1`, `Type2`  
 Любой тип, поддерживающий `operator<`, принимающую операнды определение или возвращаемого типа.  
  
 `Left`  
 Левый операнд менее чем операции.  Неспециализированный шаблон принимает аргумент ссылки значения типа `Type`.  Представляет шаблон повышает препровождение аргументов ссылки rvalue возвращаемого значения и типа `Type1`.  
  
 `Right`  
 Правый операнд менее чем операции.  Неспециализированный шаблон принимает аргумент ссылки значения типа `Type`.  Представляет шаблон повышает препровождение аргументов ссылки rvalue возвращаемого значения и типа `Type2`.  
  
## Возвращаемое значение  
 Результат `Left``<``Right`.  Представляет шаблон повышает препровождение результата, который имеет тип, который возвращается `operator<`.  
  
## Заметки  
 Бинарный предикат `less`\<`Type`\> предоставляет строгого слабое упорядочение набора значений элементов типа `Type` в классы эквивалентности, если и только в том случае, если этот тип удовлетворяют стандартные математические требования к таким образом, приказанным.  Специализацию для любого типа указателя создают полный упорядочение элементов, в котором все элементы сортируются в определенных значений относительно друг друга.  
  
## Пример  
  
```  
// functional_less.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
struct MyStruct {  
   MyStruct(int i) : m_i(i){}  
  
   bool operator < (const MyStruct & rhs) const {  
      return m_i < rhs.m_i;  
   }     
  
   int m_i;  
};  
  
int main() {  
   using namespace std;  
   vector <MyStruct> v1;  
   vector <MyStruct>::iterator Iter1;  
   vector <MyStruct>::reverse_iterator rIter1;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )       
       v1.push_back( MyStruct(rand()));  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )   
cout << Iter1->m_i << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   sort( v1.begin( ), v1.end( ), less<MyStruct>());  
  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )   
cout << Iter1->m_i << " ";  
   cout << ")" << endl;  
 }  
```  
  
## Output  
  
```  
Original vector v1 = ( 41 18467 6334 26500 19169 15724 11478 )  
Sorted vector v1 = ( 41 6334 11478 15724 18467 19169 26500 )  
```  
  
## Требования  
 **Заголовок:** \<functional\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)