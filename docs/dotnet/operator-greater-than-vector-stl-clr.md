---
title: "operator&gt; (vector) (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator> - элемент [STL/CLR]"
ms.assetid: c9c55c3f-5e82-4504-90e3-708dab7aa660
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&gt; (vector) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вектор большей, чем сравнение.  
  
## Синтаксис  
  
```  
template<typename Value>  
    bool operator>(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### Параметры  
 влево  
 Левый контейнер, с которым выполняется сравнение.  
  
 правый  
 Правой контейнер, с которым выполняется сравнение.  
  
## Заметки  
 Функция возвращает оператора `right` `<` `left`.  Он используется для выполнения приказано ли `left` после `right` при сравнении двух 2 элемент элементом.  
  
## Пример  
  
```  
// cliext_vector_operator_gt.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **B d**  
**\[B C\] \> \[B C\] false**  
**\[B d\] \> \[B C\].**   
## Требования  
 **Заголовок:**\<cliext\/vector\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [вектор](../dotnet/vector-stl-clr.md)   
 [operator\=\= \(vector\)](../Topic/operator==%20\(vector\)%20\(STL-CLR\).md)   
 [operator\!\= \(vector\)](../Topic/operator!=%20\(vector\)%20\(STL-CLR\).md)   
 [operator\< \(vector\)](../dotnet/operator-less-than-vector-stl-clr.md)   
 [operator\>\= \(vector\)](../Topic/operator%3E=%20\(vector\)%20\(STL-CLR\).md)   
 [operator\<\= \(vector\)](../dotnet/operator-less-or-equal-vector-stl-clr.md)