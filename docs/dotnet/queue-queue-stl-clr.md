---
title: "queue::queue (STL/CLR) | Microsoft Docs"
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
  - "cliext::queue::queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queue - элемент [STL/CLR]"
ms.assetid: 6106c07f-d5eb-4f0b-82df-ee4e2e751047
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queue::queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект адаптера контейнера.  
  
## Синтаксис  
  
```  
queue();  
queue(queue<Value, Container>% right);  
queue(queue<Value, Container>^ right);  
explicit queue(container_type% wrapped);  
```  
  
#### Параметры  
 правый  
 Объект, подлежащих копированию.  
  
 от программу\-оболочку  
 От программу\-оболочку контейнер, который следует использовать.  
  
## Заметки  
 Конструктор:  
  
 `queue();`  
  
 создает пустой от программу\-оболочку контейнер.  Он используется для определения начальную контролируемую пустую последовательность.  
  
 Конструктор:  
  
 `queue(queue<Value, Container>% right);`  
  
 создает от программу\-оболочку контейнер, являющийся копией `right.get_container()`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом очереди `right`.  
  
 Конструктор:  
  
 `queue(queue<Value, Container>^ right);`  
  
 создает от программу\-оболочку контейнер, являющийся копией `right->get_container()`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом очереди `*right`.  
  
 Конструктор:  
  
 `explicit queue(container_type wrapped);`  
  
 использует существующий контейнер `wrapped` как от программу\-оболочку контейнер.  Он используется для построения очередь из существующего контейнера.  
  
## Пример  
  
```  
// cliext_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/list>   
  
typedef cliext::queue<wchar_t> Myqueue;   
typedef cliext::list<wchar_t> Mylist;   
typedef cliext::queue<wchar_t, Mylist> Myqueue_list;   
int main()   
    {   
// construct an empty container   
    Myqueue c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Mylist v2(5, L'x');   
    Myqueue_list c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myqueue_list c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Myqueue_list c4(%c2);   
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
 **Заголовок:**\<cliext\/queue\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [queue](../Topic/queue%20\(STL-CLR\).md)   
 [queue::assign](../dotnet/queue-assign-stl-clr.md)   
 [queue::generic\_container](../dotnet/queue-generic-container-stl-clr.md)   
 [queue::operator\=](../dotnet/queue-operator-assign-stl-clr.md)