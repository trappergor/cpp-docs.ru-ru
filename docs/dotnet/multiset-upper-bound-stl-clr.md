---
title: "multiset::upper_bound (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::upper_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "upper_bound - член [STL/CLR]"
ms.assetid: 4a5af99f-a2a1-45be-9b01-c0055d4d0e35
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multiset::upper_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Находит конечную точку диапазона, соответствующий указанному ключу.  
  
## Синтаксис  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### Параметры  
 key  
 Значение ключа, которое необходимо найти.  
  
## Заметки  
 Функция\-член определен последний элемент `X` в контролируемой последовательности, имеет соответствующий заказ на `key`.  Если такой элемент не существует, или если `X` последний элемент в контролируемой последовательности, она возвращает [multiset::end](../dotnet/multiset-end-stl-clr.md)`()`; в противном случае она возвращает первый элемент указывает итератор, за `X`.  Он используется для поиска конец последовательности элементов в контролируемой последовательности, соответствующие указанному ключу.  
  
## Пример  
  
```  
// cliext_multiset_upper_bound.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
  **a b c**  
**upper\_bound\(L'x'\)\=\=end\(\) \= true**  
**\*upper\_bound \(L'а\) \= B**  
**\*upper\_bound \(L'б\) \= C**   
## Требования  
 **Заголовок:**\<cliext\/set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::count](../dotnet/multiset-count-stl-clr.md)   
 [multiset::equal\_range](../dotnet/multiset-equal-range-stl-clr.md)   
 [multiset::find](../Topic/multiset::find%20\(STL-CLR\).md)   
 [multiset::lower\_bound](../Topic/multiset::lower_bound%20\(STL-CLR\).md)