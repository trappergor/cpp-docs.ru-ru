---
title: "hash_set::value_compare (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare - элемент [STL/CLR]"
ms.assetid: fac89cb4-79de-44be-8ef0-202e278d0401
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# hash_set::value_compare (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Порядок делегат для 2 значений элементов.  
  
## Синтаксис  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>  
    value_compare;  
```  
  
## Заметки  
 Тип синоним для делегата, определяет порядок аргументов значение.  
  
## Пример  
  
```  
// cliext_hash_set_value_compare.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    Myhash_set::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **сравнение \(L'a, L'а\) \= true**  
**сравнение \(L'a, L'б\) \= true**  
**сравнение \(L'b, L'а\) \= false**   
## Требования  
 **Заголовок:**\<cliext\/hash\_set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::key\_compare](../Topic/hash_set::key_compare%20\(STL-CLR\).md)   
 [hash\_set::value\_comp](../dotnet/hash-set-value-comp-stl-clr.md)   
 [hash\_set::value\_type](../dotnet/hash-set-value-type-stl-clr.md)