---
title: "stack::generic_value (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack::generic_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_value - элемент [STL/CLR]"
ms.assetid: f918f5e6-5cb6-480e-8548-13e15026ffde
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# stack::generic_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тип элемента для использования с универсальным интерфейсом для контейнера.  
  
## Синтаксис  
  
```  
typedef GValue generic_value;  
```  
  
## Заметки  
 Описывает тип объекта типа `GValue`, описывающий хранимого элемента значение для использования с универсальным интерфейсом для этого класса контейнера шаблона. \(`GValue` или `value_type` или `value_type^` при `value_type` тип ссылочного.\),  
  
## Пример  
  
```  
// cliext_stack_generic_value.cpp   
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
  
// get interface to container   
    Mystack::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display in reverse using generic_value   
    for (; !gc1->empty(); gc1->pop())   
        {   
        Mystack::generic_value elem = gc1->top();   
  
        System::Console::Write(" {0}", elem);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**  
 **a B C.**   
## Требования  
 **Заголовок:**\<cliext\/stack\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [стек](../dotnet/stack-stl-clr.md)   
 [stack::generic\_container](../Topic/stack::generic_container%20\(STL-CLR\).md)   
 [stack::value\_type](../dotnet/stack-value-type-stl-clr.md)