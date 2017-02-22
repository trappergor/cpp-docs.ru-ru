---
title: "Структура random_access_iterator_tag | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xutility/std::random_access_iterator_tag"
  - "random_access_iterator_tag"
  - "std.random_access_iterator_tag"
  - "std::random_access_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "random_access_iterator_tag - класс"
  - "random_access_iterator_tag - структура"
ms.assetid: 59f5b741-c5b4-459c-ad0a-3b67cddeea23
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# Структура random_access_iterator_tag
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс, предоставляющий возвращаемый тип для функции **iterator\_category**, которая представляет произвольно\-доступный итератор.  
  
## Синтаксис  
  
```  
  
   struct random_access_iterator_tag  
: public bidirectional_iterator_tag {};  
```  
  
## Заметки  
 Классы тега категории используются как компилируют теги для выделения алгоритма.  Функции шаблона необходимо найти наиболее определенной категории своего аргумента итератора, чтобы он мог использовать наиболее эффективный алгоритм во время компиляции.  Для каждого типа итератора `Iterator`, `iterator_traits`\<`Iterator`\>**::iterator\_category** должны быть самым указанным тегом категории, описывающий расширение функциональности итератора.  
  
 Тип совпадает с **::iterator\_category** по **iterator**\<**Iter**\>**Iter** описывает объект, который можно использовать как произвольно\-доступный итератор.  
  
## Пример  
  
```  
// iterator_rait.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
#include <list>  
  
using namespace std;  
  
int main( )  
{  
   vector<int> vi;  
   vector<char> vc;  
   list<char> lc;  
   iterator_traits<vector<int>:: iterator>::iterator_category cati;  
   iterator_traits<vector<char>:: iterator>::iterator_category catc;  
   iterator_traits<list<char>:: iterator>::iterator_category catlc;  
  
   // These are both random-access iterators  
   cout << "The type of iterator for vector<int> is "  
       << "identified by the tag:\n "   
       << typeid ( cati ).name( ) << endl;  
   cout << "The type of iterator for vector<char> is "  
       << "identified by the tag:\n "   
       << typeid ( catc ).name( ) << endl;  
   if ( typeid ( cati ) == typeid( catc ) )  
      cout << "The iterators are the same." << endl << endl;  
   else  
      cout << "The iterators are not the same." << endl << endl;  
  
   // But the list iterator is bidirectinal, not random access  
   cout << "The type of iterator for list<char> is "  
       << "identified by the tag:\n "   
       << typeid (catlc).name( ) << endl;  
  
   // cout << ( typeid ( vi.begin( ) ) == typeid( vc.begin( ) ) ) << endl;  
   if ( typeid ( vi.begin( ) ) == typeid( vc.begin( ) ) )  
      cout << "The iterators are the same." << endl;  
   else  
      cout << "The iterators are not the same." << endl;  
   // A random-access iterator is a bidirectional iterator.  
   cout << ( void* ) dynamic_cast< iterator_traits<list<char>:: iterator>  
          ::iterator_category* > ( &catc ) << endl;  
}  
```  
  
## Пример результатов выполнения  
 Следующий результат для x86.  
  
```  
The type of iterator for vector<int> is identified by the tag:  
 struct std::random_access_iterator_tag  
The type of iterator for vector<char> is identified by the tag:  
 struct std::random_access_iterator_tag  
The iterators are the same.  
  
The type of iterator for list<char> is identified by the tag:  
 struct std::bidirectional_iterator_tag  
The iterators are not the same.  
0012FF3B  
```  
  
## Требования  
 **Заголовок:**\<iterator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Структура bidirectional\_iterator\_tag](../Topic/bidirectional_iterator_tag%20Struct.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)