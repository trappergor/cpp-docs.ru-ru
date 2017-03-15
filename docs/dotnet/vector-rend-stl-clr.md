---
title: "vector::rend (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::rend"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rend - член [STL/CLR]"
ms.assetid: 8dc1927f-9214-468d-877e-eda20c03e90d
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# vector::rend (STL/CLR)
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
// cliext_vector_rend.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*\-\- \-\-rend\(\) \= B**  
**\*\-\-rend\(\) \= a**  
 **x y C.**   
## Требования  
 **Заголовок:**\<cliext\/vector\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [вектор](../dotnet/vector-stl-clr.md)   
 [vector::begin](../dotnet/vector-begin-stl-clr.md)   
 [vector::end](../dotnet/vector-end-stl-clr.md)   
 [vector::rbegin](../dotnet/vector-rbegin-stl-clr.md)