---
title: "hash_multiset::rend (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::rend"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rend - член [STL/CLR]"
ms.assetid: 6d007ac9-18cc-4b51-8384-a4ff65d23e97
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# hash_multiset::rend (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Задает конец обратной управляемой последовательности.  
  
## Синтаксис  
  
```  
reverse_iterator rend();  
```  
  
## Заметки  
 Функция\-член возвращает обратный итератор, указывающий только за началом контролируемой последовательности.  Таким образом, он задает для обратной последовательности параметр `end`.  Используется для получения итератора, который задает конец управляемой последовательности с параметром `current`, отображаемой в обратном порядке, однако в случае изменения длины управляемой последовательности его состояние может измениться.  
  
## Пример  
  
```  
// cliext_hash_multiset_rend.cpp   
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
  
// inspect first two items   
    Myhash_multiset::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*\-\- \-\-rend\(\) \= B**  
**\*\-\-rend\(\) \= a**   
## Требования  
 **Заголовок:**\<cliext\/hash\_set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::begin](../dotnet/hash-multiset-begin-stl-clr.md)   
 [hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)   
 [hash\_multiset::rbegin](../Topic/hash_multiset::rbegin%20\(STL-CLR\).md)