---
title: "map::lower_bound (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::lower_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lower_bound - член [STL/CLR]"
ms.assetid: 959651a0-f949-4cc1-859b-248b6930f16c
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# map::lower_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Находит начало диапазона, соответствующий указанному ключу.  
  
## Синтаксис  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### Параметры  
 key  
 Значение ключа, которое необходимо найти.  
  
## Заметки  
 Функция\-член определяет первый элемент `X` в контролируемой последовательности, имеет соответствующий заказ на `key`.  Если такой элемент не существует, возвращается [map::end](../dotnet/map-end-stl-clr.md)`()`; в противном случае возвращается итератор, обозначает `X`.  Он используется для поиска начало последовательности элементов в контролируемой последовательности, соответствующие указанному ключу.  
  
## Пример  
  
```  
// cliext_map_lower_bound.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    Mymap::iterator it = c1.lower_bound(L'a');   
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.lower_bound(L'b');   
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[BC — 3\]**  
**lower\_bound\(L'x'\)\=\=end\(\) \= true**  
**\*lower\_bound \(L'а\) \= \[1\]**  
**\*lower\_bound \(L'б\) \= \[B 2\]**   
## Требования  
 **Заголовок:**\<cliext\/map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [map](../dotnet/map-stl-clr.md)   
 [map::count](../dotnet/map-count-stl-clr.md)   
 [map::equal\_range](../dotnet/map-equal-range-stl-clr.md)   
 [map::find](../Topic/map::find%20\(STL-CLR\).md)   
 [map::upper\_bound](../dotnet/map-upper-bound-stl-clr.md)