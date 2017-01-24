---
title: "multiset::value_comp (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::value_comp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_comp - член [STL/CLR]"
ms.assetid: 6b418e7a-9e82-4d35-a25d-f07b79a875a6
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::value_comp (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Копирует порядок делегат для 2 значений элементов.  
  
## Синтаксис  
  
```  
value_compare^ value_comp();  
```  
  
## Заметки  
 Возвращает порядок функцию\-член делегат, используемый для сортировки контролируемую последовательность.  Он используется для сравнения значений 2 элемента.  
  
## Пример  
  
```  
// cliext_multiset_value_comp.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::value_compare^ kcomp = c1.value_comp();   
  
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
  
  **сравнение \(L'a, L'а\) \= false**  
**сравнение \(L'a, L'б\) \= true**  
**сравнение \(L'b, L'а\) \= false**   
## Требования  
 **Заголовок:**\<cliext\/set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::value\_compare](../Topic/multiset::value_compare%20\(STL-CLR\).md)   
 [multiset::value\_type](../dotnet/multiset-value-type-stl-clr.md)