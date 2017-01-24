---
title: "hash_multiset::find (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multiset::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find - член [STL/CLR]"
ms.assetid: fbedeb37-242e-4c2a-b1f8-234bcfd9cd25
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multiset::find (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет элемент, соответствующий указанному ключу.  
  
## Синтаксис  
  
```  
iterator find(key_type key);  
```  
  
#### Параметры  
 key  
 Значение ключа, которое необходимо найти.  
  
## Заметки  
 Если хотя бы один элемент в контролируемой последовательности имеет соответствующий заказ с `key`, функцию\-член возвращает итератор обозначая один из этих элементов; в противном случае возвращается [hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)`()`.  Он используется, чтобы найти элемент в данный момент в контролируемой последовательности, которая соответствует указанному ключу.  
  
## Пример  
  
```  
// cliext_hash_multiset_find.cpp   
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
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**найдите a \= false**  
**найдите B \= B**  
**найдите C \= false**   
## Описание  
 Обратите внимание, что `find` не гарантирует, что из нескольких находит элемент.  
  
## Требования  
 **Заголовок:**\<cliext\/hash\_set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::equal\_range](../Topic/hash_multiset::equal_range%20\(STL-CLR\).md)   
 [hash\_multiset::lower\_bound](../Topic/hash_multiset::lower_bound%20\(STL-CLR\).md)   
 [hash\_multiset::upper\_bound](../dotnet/hash-multiset-upper-bound-stl-clr.md)