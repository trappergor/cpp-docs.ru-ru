---
title: "deque::rbegin (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::rbegin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rbegin - член [STL/CLR]"
ms.assetid: 5d399c1d-bd7e-4b2e-bde0-11a000e29679
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# deque::rbegin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Задает начало обратной управляемой последовательности.  
  
## Синтаксис  
  
```  
reverse_iterator rbegin();  
```  
  
## Заметки  
 Функция\-член возвращает обратный итератор, обозначает последний элемент контролируемой последовательности или только за началом пустой последовательности.  Таким образом, он задает для обратной последовательности параметр `beginning`.  Используется для получения итератора, который задает начало управляемой последовательности с параметром `current`, отображаемой в обратном порядке, однако в случае изменения длины управляемой последовательности его состояние может измениться.  
  
## Пример  
  
```  
// cliext_deque_rbegin.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*rbegin\(\) \= C**  
**\*\+\+rbegin\(\) \= B**  
 **x y**   
## Требования  
 **Заголовок:**\<cliext\/deque\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::begin](../dotnet/deque-begin-stl-clr.md)   
 [deque::end](../Topic/deque::end%20\(STL-CLR\).md)   
 [deque::rend](../Topic/deque::rend%20\(STL-CLR\).md)