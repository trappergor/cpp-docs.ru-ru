---
title: "list::list (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элемент списка [STL/CLR]"
ms.assetid: 51b58f63-c65a-4d54-b746-0c10635b123b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::list (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект контейнера.  
  
## Синтаксис  
  
```  
list();  
list(list<Value>% right);  
list(list<Value>^ right);  
explicit list(size_type count);  
list(size_type count, value_type val);  
template<typename InIt>  
    list(InIt first, InIt last);  
list(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### Параметры  
 count  
 Число элементов, который необходимо вставить.  
  
 first  
 Начало диапазона, который необходимо вставить.  
  
 last  
 Элемент диапазона, который необходимо вставить.  
  
 правый  
 Объект или диапазон для вставки.  
  
 val  
 Значение элемента, который необходимо вставить.  
  
## Заметки  
 Конструктор:  
  
 `list();`  
  
 инициализирует контролируемая последовательность без элементов.  Он используется для определения начальную контролируемую пустую последовательность.  
  
 Конструктор:  
  
 `list(list<Value>% right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``.`[list::begin](../Topic/list::begin%20\(STL-CLR\).md)`(),` `right``.`[list::end](../Topic/list::end%20\(STL-CLR\).md)`())`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `right` списка.  
  
 Конструктор:  
  
 `list(list<Value>^ right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``->`[list::begin](../Topic/list::begin%20\(STL-CLR\).md)`(),` `right``->`[list::end](../Topic/list::end%20\(STL-CLR\).md)`())`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом списка дескриптор которого `right`.  
  
 Конструктор:  
  
 `explicit list(size_type count);`  
  
 инициализирует контролируемая последовательность с элементами `count` каждое со значением `value_type()`.  Он используется для заполнения контейнер с элементами, все значения по умолчанию.  
  
 Конструктор:  
  
 `list(size_type count, value_type val);`  
  
 инициализирует контролируемая последовательность с элементами `count` каждое со значением `val`.  Он используется для заполнения контейнер с элементами, все одно и то же значение.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `list(InIt first, InIt last);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности.  
  
 Конструктор:  
  
 `list(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем.  
  
## Пример  
  
```  
// cliext_list_construct.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::list<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::list<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::list<wchar_t>::iterator it = c3.end();   
    cliext::list<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::list<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::list<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0**  
 **x x x x x x**  
 **x x x x x**  
 **x x x x x x**  
 **x x x x x x**  
 **x x x x x x**   
## Требования  
 **Заголовок:**\<cliext\/list\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [list](../dotnet/list-stl-clr.md)   
 [list::assign](../dotnet/list-assign-stl-clr.md)   
 [list::generic\_container](../dotnet/list-generic-container-stl-clr.md)   
 [list::operator\=](../dotnet/list-operator-assign-stl-clr.md)