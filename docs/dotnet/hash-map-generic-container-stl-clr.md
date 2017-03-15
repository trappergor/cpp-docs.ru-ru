---
title: "hash_map::generic_container (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::generic_container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_container - элемент [STL/CLR]"
ms.assetid: 82014d95-7804-475a-86c2-649caaa4a8bc
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# hash_map::generic_container (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тип универсального интерфейса для контейнера.  
  
## Синтаксис  
  
```  
typedef Microsoft::VisualC::StlClr::  
    IHash<GKey, GValue>  
    generic_container;  
```  
  
## Заметки  
 Описывает тип универсальный интерфейс для этого класса контейнера шаблона.  
  
## Пример  
  
```  
// cliext_hash_map_generic_container.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Myhash_map::generic_container^ gc1 = %c1;   
    for each (Myhash_map::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(Myhash_map::make_value(L'd', 4));   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.insert(Myhash_map::make_value(L'e', 5));   
    for each (Myhash_map::value_type elem in gc1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[BC — 3\]**  
 **\[1\] \[2\] \[BC — 3\]**  
 **\[1\] \[2\] \[B C \[3\]4 d\]**  
 **\[1\] \[2\] B C \[3\] \[4\] \[de 5\]**   
## Требования  
 **Заголовок:**\<cliext\/hash\_map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::generic\_iterator](../dotnet/hash-map-generic-iterator-stl-clr.md)