---
title: "list::back (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::back"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back - член [STL/CLR]"
ms.assetid: 3241e497-42ab-4108-8598-3f90eac76f07
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# list::back (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает последний элемент.  
  
## Синтаксис  
  
```  
reference back();  
```  
  
## Заметки  
 Возвращает ссылку на функцию\-член последнему элементу контролируемой последовательности, которая должна быть непустой.  Он используется для получения последнего элемента, если известно, что он существует.  
  
## Пример  
  
```  
// cliext_list_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**back\(\) \= C**  
 **B x**   
## Требования  
 **Заголовок:**\<cliext\/list\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [list](../dotnet/list-stl-clr.md)   
 [list::back\_item](../Topic/list::back_item%20\(STL-CLR\).md)   
 [list::front](../dotnet/list-front-stl-clr.md)   
 [list::front\_item](../dotnet/list-front-item-stl-clr.md)