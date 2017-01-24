---
title: "hash_set::end (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_set::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end - член [STL/CLR]"
ms.assetid: 957de04e-fdc1-4295-ba25-8b0ad1ea97de
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::end (STL/CLR)
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
// cliext_hash_set_end.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Myhash_set::iterator it = c1.end();   
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
 **Заголовок:**\<cliext\/hash\_set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)