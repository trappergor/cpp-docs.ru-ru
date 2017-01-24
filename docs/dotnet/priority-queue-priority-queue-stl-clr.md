---
title: "priority_queue::priority_queue (STL/CLR) | Microsoft Docs"
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
  - "cliext::priority_queue::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "priority_queue - элемент [STL/CLR]"
ms.assetid: aab423d7-959e-48fd-9028-e9f45f43cb8a
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# priority_queue::priority_queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект адаптера контейнера.  
  
## Синтаксис  
  
```  
priority_queue();  
priority_queue(priority_queue<Value, Container> right);  
priority_queue(priority_queue<Value, Container> right);  
explicit priority_queue(value_compare^ pred);  
priority_queue(value_compare^ pred, container_type% cont);  
template<typename InIt>  
    priority_queue(InIt first, InIt last);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred, container_type% cont);  
```  
  
#### Параметры  
 cont  
 Контейнер, которые необходимо скопировать.  
  
 first  
 Начало диапазона, который необходимо вставить.  
  
 last  
 Элемент диапазона, который необходимо вставить.  
  
 pred  
 Порядок предикат для контролируемой последовательности.  
  
 правый  
 Объект или диапазон для вставки.  
  
## Заметки  
 Конструктор:  
  
 `priority_queue();`  
  
 создает пустой от программу\-оболочку контейнер с предикатом по умолчанию порядок.  Он используется, чтобы указать пустую последовательность, начальную контролируемую с предикатом по умолчанию порядок.  
  
 Конструктор:  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 создает от программу\-оболочку контейнер, являющийся копией `right.get_container()`, порядок с предикатом `right.value_comp()`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом очереди `right`, с тем же заказу предикатом.  
  
 Конструктор:  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 создает от программу\-оболочку контейнер, являющийся копией `right->get_container()`, порядок с предикатом `right->value_comp()`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом очереди `*right`, с тем же заказу предикатом.  
  
 Конструктор:  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 создает пустой от программу\-оболочку контейнер, порядок с предикатом `pred`.  Он используется для определения начальную контролируемую пустую последовательность, указанным при упорядочивании предикатом.  
  
 Конструктор:  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 создает пустой от программу\-оболочку контейнер, порядок с предикатом `pred`, а затем отправляет все элементы `cont` он используется, чтобы определить домашнюю контролируемую последовательность из существующего контейнера, указанным при упорядочивании предикатом.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last);`  
  
 создает пустой от программу\-оболочку контейнер с предикатом по умолчанию порядок, а затем отправляет последовательность `[``first``,` `last``)`.  Он используется, чтобы определить домашнюю контролируемую последовательность из указанного eqeuence, указанным при упорядочивании предикатом.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last,`  
  
 `value_compare^ pred);`  
  
 создает пустой от программу\-оболочку контейнер, порядок с предикатом `pred`, а затем отправляет последовательность `[``first``,` `last``)`.  Он используется, чтобы определить домашнюю контролируемую последовательность из указанного seqeuence, указанным при упорядочивании предикатом.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `priority_queue(InIt first, InIt last,`  
  
 `value_compare^ pred, container_type% cont);`  
  
 создает пустой от программу\-оболочку контейнер, порядок с предикатом `pred`, а затем отправляет все элементы `cont` и последовательность `[``first``,` `last``)`.  Он используется, чтобы определить домашнюю контролируемую последовательность из существующего контейнера и заданного seqeuence, указанным при упорядочивании предикатом.  
  
## Пример  
  
```  
// cliext_priority_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/deque>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
typedef cliext::deque<wchar_t> Mydeque;   
int main()   
    {   
// construct an empty container   
    Mypriority_queue c1;   
    Mypriority_queue::container_type^ wc1 = c1.get_container();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    for each (wchar_t elem in wc1)   
        c2.push(elem);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule by copying an underlying container   
    Mypriority_queue c2x =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
   for each (wchar_t elem in c2x.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mypriority_queue c3(wc1->begin(), wc1->end());   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mypriority_queue c4(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>());   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range, another container, and an ordering rule   
    Mypriority_queue c5(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c5.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mypriority_queue c6(c3);   
    for each (wchar_t elem in c6.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mypriority_queue c7(%c3);   
    for each (wchar_t elem in c7.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule, by copying an underlying container   
    Mypriority_queue c8 =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c8.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **B C.**  
**size\(\) \= 0**  
 **a c b**  
 **a c b**  
 **B C.**  
 **a c b**  
 **a a b c c b**  
 **B C.**  
 **B C.**  
 **a c b**   
## Требования  
 **Заголовок:**\<cliext\/queue\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [priority\_queue::assign](../dotnet/priority-queue-assign-stl-clr.md)   
 [priority\_queue::generic\_container](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority\_queue::operator\=](../dotnet/priority-queue-operator-assign-stl-clr.md)