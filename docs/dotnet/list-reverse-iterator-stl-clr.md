---
title: "list::reverse_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator - элемент [STL/CLR]"
ms.assetid: 56853ed8-cb12-41d7-98b2-c511cd77945d
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# list::reverse_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тип обратного итератора для контролируемой последовательности.  
  
## Синтаксис  
  
```  
typedef T3 reverse_iterator;  
```  
  
## Заметки  
 Описывает тип объекта неспецифицированного типа `T3`, который можно использовать в качестве обратного итератор для контролируемой последовательности.  
  
## Пример  
  
```  
// cliext_list_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    rit = c1.rbegin();   
    *rit = L'x';   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a B C.**  
 **x a B**   
## Требования  
 **Заголовок:**\<cliext\/list\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [list](../dotnet/list-stl-clr.md)   
 [list::const\_iterator](../dotnet/list-const-iterator-stl-clr.md)   
 [list::const\_reverse\_iterator](../dotnet/list-const-reverse-iterator-stl-clr.md)   
 [list::iterator](../dotnet/list-iterator-stl-clr.md)