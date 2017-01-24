---
title: "set::find (STL/CLR) | Microsoft Docs"
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
  - "cliext::set::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find - член [STL/CLR]"
ms.assetid: 916e581c-2815-4c07-a51a-6c5ddfa730c1
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# set::find (STL/CLR)
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
 Если хотя бы один элемент в контролируемой последовательности имеет соответствующий заказ с `key`, функцию\-член возвращает итератор обозначая один из этих элементов; в противном случае возвращается [set::end](../dotnet/set-end-stl-clr.md)`()`.  Он используется, чтобы найти элемент в данный момент в контролируемой последовательности, которая соответствует указанному ключу.  
  
## Пример  
  
```  
// cliext_set_find.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
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
 **Заголовок:**\<cliext\/set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [набор](../dotnet/set-stl-clr.md)   
 [set::equal\_range](../dotnet/set-equal-range-stl-clr.md)   
 [set::lower\_bound](../Topic/set::lower_bound%20\(STL-CLR\).md)   
 [set::upper\_bound](../Topic/set::upper_bound%20\(STL-CLR\).md)