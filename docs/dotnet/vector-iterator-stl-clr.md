---
title: "vector::iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator - элемент [STL/CLR]"
ms.assetid: a99932ac-c29e-4851-9331-9367f4dd9440
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# vector::iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тип итератора для управляемой последовательности.  
  
## Синтаксис  
  
```  
typedef T1 iterator;  
```  
  
## Заметки  
 Описывает тип объекта неспецифицированного типа `T1`, который можно использовать как произвольно\-доступный итератор для контролируемой последовательности.  
  
## Пример  
  
```  
// cliext_vector_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    it = c1.begin();   
    *it = L'x';   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **x B C.**   
## Требования  
 **Заголовок:**\<cliext\/vector\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [вектор](../dotnet/vector-stl-clr.md)   
 [vector::const\_iterator](../dotnet/vector-const-iterator-stl-clr.md)