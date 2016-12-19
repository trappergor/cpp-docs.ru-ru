---
title: "deque::deque (STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "deque - элемент [STL/CLR]"
ms.assetid: e5bc9511-619e-469c-b50a-e06858e7fce7
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::deque (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект контейнера.  
  
## Синтаксис  
  
```  
deque();  
deque(deque<Value>% right);  
deque(deque<Value>^ right);  
explicit deque(size_type count);  
deque(size_type count, value_type val);  
template<typename InIt>  
    deque(InIt first, InIt last);  
deque(System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
 `deque();`  
  
 инициализирует контролируемая последовательность без элементов.  Он используется для определения начальную контролируемую пустую последовательность.  
  
 Конструктор:  
  
 `deque(deque<Value>% right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``.`[deque::begin](../dotnet/deque-begin-stl-clr.md)`(),` `right``.`[deque::end](../Topic/deque::end%20\(STL-CLR\).md)`())`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `right` deque.  
  
 Конструктор:  
  
 `deque(deque<Value>^ right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``->`[deque::begin](../dotnet/deque-begin-stl-clr.md)`(),` `right``->`[deque::end](../Topic/deque::end%20\(STL-CLR\).md)`())`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом deque дескриптор которого `right`.  
  
 Конструктор:  
  
 `explicit deque(size_type count);`  
  
 инициализирует контролируемая последовательность с элементами `count` каждое со значением `value_type()`.  Он используется для заполнения контейнер с элементами, все значения по умолчанию.  
  
 Конструктор:  
  
 `deque(size_type count, value_type val);`  
  
 инициализирует контролируемая последовательность с элементами `count` каждое со значением `val`.  Он используется для заполнения контейнер с элементами, все одно и то же значение.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `deque(InIt first, InIt last);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности.  
  
 Конструктор:  
  
 `deque(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем.  
  
## Пример  
  
```  
// cliext_deque_construct.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::deque<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::deque<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::deque<wchar_t>::iterator it = c3.end();   
    cliext::deque<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::deque<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::deque<wchar_t> c8(%c3);   
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
 **Заголовок:**\<cliext\/deque\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::assign](../dotnet/deque-assign-stl-clr.md)   
 [deque::generic\_container](../Topic/deque::generic_container%20\(STL-CLR\).md)   
 [operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)