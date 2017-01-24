---
title: "stack::stack (STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stack - элемент [STL/CLR]"
ms.assetid: f1cfb3fe-4d22-41e5-906b-e8faa0bcde9b
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stack::stack (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект адаптера контейнера.  
  
## Синтаксис  
  
```  
stack();  
stack(stack<Value, Container>% right);  
stack(stack<Value, Container>^ right);  
explicit stack(container_type% wrapped);  
```  
  
#### Параметры  
 правый  
 Объект, подлежащих копированию.  
  
 от программу\-оболочку  
 От программу\-оболочку контейнер, который следует использовать.  
  
## Заметки  
 Конструктор:  
  
 `stack();`  
  
 создает пустой от программу\-оболочку контейнер.  Он используется для определения начальную контролируемую пустую последовательность.  
  
 Конструктор:  
  
 `stack(stack<Value, Container>% right);`  
  
 создает от программу\-оболочку контейнер, являющийся копией `right.get_container()`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `right` стека.  
  
 Конструктор:  
  
 `stack(stack<Value, Container>^ right);`  
  
 создает от программу\-оболочку контейнер, являющийся копией `right->get_container()`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `*right` стека.  
  
 Конструктор:  
  
 `explicit stack(container_type% wrapped);`  
  
 использует существующий контейнер `wrapped` как от программу\-оболочку контейнер.  Он используется для построения стека из существующего контейнера.  
  
## Пример  
  
```  
// cliext_stack_construct.cpp   
// compile with: /clr   
#include <cliext/stack>   
#include <cliext/vector>   
  
typedef cliext::stack<wchar_t> Mystack;   
typedef cliext::vector<wchar_t> Myvector;   
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;   
int main()   
    {   
// construct an empty container   
    Mystack c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Myvector v2(5, L'x');   
    Mystack_vec c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mystack_vec c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Mystack_vec c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **x x x x x**  
 **x x x x x**  
 **x x x x x**   
## Требования  
 **Заголовок:**\<cliext\/stack\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [стек](../dotnet/stack-stl-clr.md)   
 [stack::assign](../Topic/stack::assign%20\(STL-CLR\).md)   
 [stack::generic\_container](../Topic/stack::generic_container%20\(STL-CLR\).md)   
 [stack::operator\=](../dotnet/stack-operator-assign-stl-clr.md)