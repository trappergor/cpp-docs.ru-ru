---
title: "Класс indirect_array | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.indirect_array"
  - "valarray/std::indirect_array"
  - "std::indirect_array"
  - "indirect_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "indirect_array - класс"
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс indirect_array
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Внутренний вспомогательный класс шаблона, который поддерживает объекты, valarrays подмножества, обеспечивая операций между массивами подмножества, задавая подмножество индексов родительского valarray.  
  
## Синтаксис  
  
```  
template<class Type>  
   class indirect_array {  
public:  
   typedef Type value_type;  
   void operator=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator=(  
      const Type& x  
   ) const;  
  
   void operator*=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator/=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator%=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator+=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator-=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator^=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator&=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator|=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator<<=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator>>=(  
      const valarray<Type>& x  
   ) const;  
  
// The rest is private or implementation defined  
}  
```  
  
## Заметки  
 Класс описывает объект, который содержит ссылку на объект **va** класса [valarray](../standard-library/valarray-class.md)**\<Type\>** вместе с объектом **xa** класса **valarray\<size\_t\>**, который описывает последовательность элементов, чтобы выделить из объекта **valarray\<Type\>**.  
  
 При создании объекта **indirect\_array\<Type\>** только путем написания выражение в форме **va\[xa\]**.  Функции\-члены класса indirect\_array затем аналогично поведению соответствующий сигнатуры функции, определенные для **valarray\<Type\>**, за исключением того, что только последовательность выбранных элементов относится.  
  
 Последовательность состоит из элементов **xa.**, где элемент [size](../Topic/valarray::size.md)`I` будет индексом **xa**\[`I`\] внутри **va**.  
  
## Пример:  
  
```  
// indirect_array.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      va [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      va [ i ] =  -1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   // Select 2nd, 4th & 6th elements  
   // and assign a value of 10 to them  
   valarray<size_t> indx ( 3 );  
   indx [0] = 2;  
   indx [1] = 4;  
   indx [2] = 6;  
   va[indx] = 10;  
  
   cout << "The modified operand valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
### Output  
  
```  
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).  
The modified operand valarray is:  ( 0 -1 10 -1 10 -1 10 -1 8 -1 ).  
```  
  
## Требования  
 **Заголовок:**\<valarray\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)