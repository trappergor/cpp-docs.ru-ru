---
title: "map::operator(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operatormember [] [STL/CLR]"
ms.assetid: 50e494c5-62d4-4469-8da3-7432ee4dff97
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# map::operator(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Сопоставляет ключ, связанный с его сопоставлянному значение.  
  
## Синтаксис  
  
```  
mapped_type operator[](key_type key);  
```  
  
#### Параметры  
 key  
 Значение ключа, которое необходимо найти.  
  
## Заметки  
 Функции\-члены стремятся найти элемент с соответствующий заказ на `key`.  При обнаружении одно, возвращается сопоставляются связанное значение; в противном случае он содержит `value_type(``key``, mapped_type())` и возвращает соответствующее \(по умолчанию\) сопоставляются значению.  Он используется, чтобы искать сопоставляются значение заданного его связанный ключ, или убедиться, что запись существует для ключа, если не найдено.  
  
## Пример  
  
```  
// cliext_map_operator_sub.cpp   
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
  
    System::Console::WriteLine("c1[{0}] = {1}",   
        L'A', c1[L'A']);   
    System::Console::WriteLine("c1[{0}] = {1}",   
        L'b', c1[L'b']);   
  
// redisplay altered contents   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// alter mapped values and redisplay   
    c1[L'A'] = 10;   
    c1[L'c'] = 13;   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[BC — 3\]**  
**a \[c1\] \= 0**  
**c1\] \[B \= 2**  
 **A \[0\] \[1\] \[2\] \[BC — 3\]**  
 **\[A10\] \[1\] \[2\] \[BC — 13\]**   
## Требования  
 **Заголовок:**\<cliext\/map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [map](../dotnet/map-stl-clr.md)   
 [map::find](../Topic/map::find%20\(STL-CLR\).md)   
 [map::insert](../dotnet/map-insert-stl-clr.md)