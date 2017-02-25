---
title: "hash_map::make_value (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value - элемент [STL/CLR]"
ms.assetid: 1fcdcacc-5edf-46b7-9481-9a4aef32b025
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# hash_map::make_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект значение.  
  
## Синтаксис  
  
```  
static value_type make_value(key_type key, mapped_type mapped);  
```  
  
#### Параметры  
 key  
 Значение ключа, который следует использовать.  
  
 сопоставленного  
 Сопоставляемое значение, которое необходимо найти.  
  
## Заметки  
 Функция\-член возвращает объект `value_type` ключ которого `key`, а сопоставленной значение `mapped`.  Он используется, формирующих объект, подходящий для использования с несколькими функциях\-членах.  
  
## Пример  
  
```  
// cliext_hash_map_make_value.cpp   
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
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[BC — 3\]**   
## Требования  
 **Заголовок:**\<cliext\/hash\_map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::key\_type](../Topic/hash_map::key_type%20\(STL-CLR\).md)   
 [hash\_map::mapped\_type](../Topic/hash_map::mapped_type%20\(STL-CLR\).md)   
 [hash\_map::value\_type](../dotnet/hash-map-value-type-stl-clr.md)