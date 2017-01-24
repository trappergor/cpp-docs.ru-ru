---
title: "hash_multimap::reverse_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator - элемент [STL/CLR]"
ms.assetid: 000d3250-befa-4604-b042-11424cb179dc
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap::reverse_iterator (STL/CLR)
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
// cliext_hash_multimap_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" reversed   
    Myhash_multimap::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" [{0} {1}]", rit->first, rit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **C \[3\] \[2\] \[B1\]**   
## Требования  
 **Заголовок:**\<cliext\/hash\_map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::const\_iterator](../dotnet/hash-multimap-const-iterator-stl-clr.md)   
 [hash\_multimap::const\_reverse\_iterator](../Topic/hash_multimap::const_reverse_iterator%20\(STL-CLR\).md)   
 [hash\_multimap::iterator](../dotnet/hash-multimap-iterator-stl-clr.md)