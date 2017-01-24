---
title: "operator&lt; (vector) (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator< - элемент [STL/CLR]"
ms.assetid: 41fbd028-e937-4337-9429-57e79a993eef
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt; (vector) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вектор проведения сравнения.  
  
## Синтаксис  
  
```  
template<typename Value>  
    bool operator<(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### Параметры  
 влево  
 Левый контейнер, с которым выполняется сравнение.  
  
 правый  
 Правой контейнер, с которым выполняется сравнение.  
  
## Заметки  
 Функция возвращает значение true, если оператора для самой низкой позиции `i`, которая `!(``right``[i] <` `left``[i])` также имеет значение true, `left``[i] <` `right``[i]`.  В противном случае возвращается `left``->size() <` `right``->size()` его использовании для выполнения приказано ли `left` до 2 `right` при сравнении двух элемент элементом.  
  
## Пример  
  
```  
// cliext_vector_operator_lt.cpp   
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
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **B d**  
**\[B C\] \< \[B C\] принимает значение " false "**  
**\[\-\] \< \[B C d\] наоборот B**   
## Требования  
 **Заголовок:**\<cliext\/vector\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [вектор](../dotnet/vector-stl-clr.md)   
 [operator\=\= \(vector\)](../Topic/operator==%20\(vector\)%20\(STL-CLR\).md)   
 [operator\!\= \(vector\)](../Topic/operator!=%20\(vector\)%20\(STL-CLR\).md)   
 [operator\>\= \(vector\)](../Topic/operator%3E=%20\(vector\)%20\(STL-CLR\).md)   
 [operator\> \(vector\)](../dotnet/operator-greater-than-vector-stl-clr.md)   
 [operator\<\= \(vector\)](../dotnet/operator-less-or-equal-vector-stl-clr.md)