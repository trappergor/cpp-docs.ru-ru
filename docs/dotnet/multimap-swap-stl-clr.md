---
title: "multimap::swap (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap - член [STL/CLR]"
ms.assetid: 198018d2-7814-4237-8ec3-5f3ea950e8af
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multimap::swap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Меняет местами содержимое двух контейнеров.  
  
## Синтаксис  
  
```  
void swap(multimap<Key, Mapped>% right);  
```  
  
#### Параметры  
 правый  
 Контейнер для обмена содержимым.  
  
## Заметки  
 Меняет местами функции\-члена из последовательности между `this` и `right`.  Это происходит при расчете времени и не создает исключений.  Он используется как быстрый способ обмена содержимое 2 контейнеров.  
  
## Пример  
  
```  
// cliext_multimap_swap.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    Mymultimap c2;   
    c2.insert(Mymultimap::make_value(L'd', 4));   
    c2.insert(Mymultimap::make_value(L'e', 5));   
    c2.insert(Mymultimap::make_value(L'f', 6));   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[BC — 3\]**  
 **\[d: 4\] \[5\] \[ef 6\]**  
 **\[d: 4\] \[5\] \[ef 6\]**  
 **\[1\] \[2\] \[BC — 3\]**   
## Требования  
 **Заголовок:**\<cliext\/map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::operator\=](../dotnet/multimap-operator-assign-stl-clr.md)