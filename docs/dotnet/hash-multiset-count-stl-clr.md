---
title: "hash_multiset::count (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::count"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "count - член [STL/CLR]"
ms.assetid: 2b31e6b6-3f2c-4042-a06d-90d3074aad43
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multiset::count (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Находит число элементов, соответствующие указанному ключу.  
  
## Синтаксис  
  
```  
size_type count(key_type key);  
```  
  
#### Параметры  
 key  
 Значение ключа, которое необходимо найти.  
  
## Заметки  
 Функция\-член возвращает количество элементов в соответствующий контролируемой последовательности, имеющие осуществляется с `key`.  Используется для определения количества элементов в управляемой последовательности, ключ которых в данный момент совпадает с заданным ключом.  
  
## Пример  
  
```  
// cliext_hash_multiset_count.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
  **a b c**  
**число \(L'A\) \= 0**  
**число \(L'б\) \= 1**  
**число L'C \(\-\) \= 0**   
## Требования  
 **Заголовок:**\<cliext\/hash\_set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::equal\_range](../Topic/hash_multiset::equal_range%20\(STL-CLR\).md)