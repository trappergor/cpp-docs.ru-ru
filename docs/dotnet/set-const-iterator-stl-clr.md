---
title: "set::const_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::const_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_iterator - элемент [STL/CLR]"
ms.assetid: de234ad4-d420-4da8-a13a-1aec8c337d8b
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# set::const_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тип постоянного итератора для управляемой последовательности.  
  
## Синтаксис  
  
```  
typedef T2 const_iterator;  
```  
  
## Заметки  
 Описывает тип объекта неспецифицированного типа `T2`, который можно использовать как постоянный двунаправленный итератор для контролируемой последовательности.  
  
## Пример  
  
```  
// cliext_set_const_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Myset::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## Требования  
 **Заголовок:**\<cliext\/set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [набор](../dotnet/set-stl-clr.md)   
 [set::iterator](../Topic/set::iterator%20\(STL-CLR\).md)