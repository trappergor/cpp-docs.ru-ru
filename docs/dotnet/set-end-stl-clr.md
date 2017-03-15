---
title: "set::end (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end - член [STL/CLR]"
ms.assetid: 3fe66e73-5eb9-4972-8a07-01f2eb4d1ccb
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# set::end (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Задает конец управляемой последовательности.  
  
## Синтаксис  
  
```  
iterator end();  
```  
  
## Заметки  
 Функция\-член возвращает двунаправленный итератор, указывающий только за пределы контролируемой последовательности.  Он используется для получения итератор, обозначает конец контролируемой последовательности; это изменение doesn состояния не изменяется, если длина контролируемой последовательности.  
  
## Пример  
  
```  
// cliext_set_end.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Myset::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*\-\- \-\-end\(\) \= B**  
**\*\-\-end\(\) \= C**   
## Требования  
 **Заголовок:**\<cliext\/set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [набор](../dotnet/set-stl-clr.md)   
 [set::begin](../dotnet/set-begin-stl-clr.md)