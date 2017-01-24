---
title: "operator&lt;= (stack) (STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::operator<="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator<= - элемент [STL/CLR]"
ms.assetid: fd2f500b-84d1-4eed-98ba-3a6f481ae8f5
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt;= (stack) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Стека больше или равное сравнение.  
  
## Синтаксис  
  
```  
template<typename Value,  
    typename Container>  
    bool operator<=(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### Параметры  
 влево  
 Левый контейнер, с которым выполняется сравнение.  
  
 правый  
 Правой контейнер, с которым выполняется сравнение.  
  
## Заметки  
 Функция возвращает оператора `!(``right` `<` `left``)`.  Он используется для выполнения не приказано ли `left` после `right` при сравнении 2 стека элемент элементом.  
  
## Пример  
  
```  
// cliext_stack_operator_le.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **B d**  
**\[B C\] \<\= \[B C\] оказывается**  
**\[B d\] \<\= \[B C\] ложен**   
## Требования  
 **Заголовок:**\<cliext\/stack\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [стек](../dotnet/stack-stl-clr.md)   
 [operator\=\= \(stack\)](../dotnet/operator-equality-stack-stl-clr.md)   
 [operator\!\= \(stack\)](../dotnet/operator-inequality-stack-stl-clr.md)   
 [operator\< \(stack\)](../dotnet/operator-less-than-stack-stl-clr.md)   
 [operator\>\= \(stack\)](../Topic/operator%3E=%20\(stack\)%20\(STL-CLR\).md)   
 [operator\> \(stack\)](../dotnet/operator-greater-than-stack-stl-clr.md)