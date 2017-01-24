---
title: "vector::vector (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector - элемент [STL/CLR]"
ms.assetid: a0b5e807-1ef2-422b-b772-1f96cd62fb51
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::vector (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект контейнера.  
  
## Синтаксис  
  
```  
vector();  
vector(vector<Value>% right);  
vector(vector<Value>^ right);  
explicit vector(size_type count);  
vector(size_type count, value_type val);  
template<typename InIt>  
    vector(InIt first, InIt last);  
vector(System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
 `vector();`  
  
 инициализирует контролируемая последовательность без элементов.  Он используется для определения начальную контролируемую пустую последовательность.  
  
 Конструктор:  
  
 `vector(vector<Value>% right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``.`[vector::begin](../dotnet/vector-begin-stl-clr.md)`(),` `right``.`[vector::end](../dotnet/vector-end-stl-clr.md)`())`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `right` вектора.  
  
 Конструктор:  
  
 `vector(vector<Value>^ right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``->`[vector::begin](../dotnet/vector-begin-stl-clr.md)`(),` `right``->`[vector::end](../dotnet/vector-end-stl-clr.md)`())`.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом вектора дескриптор которого `right`.  
  
 Конструктор:  
  
 `explicit vector(size_type count);`  
  
 инициализирует контролируемая последовательность с элементами `count` каждое со значением `value_type()`.  Он используется для заполнения контейнер с элементами, все значения по умолчанию.  
  
 Конструктор:  
  
 `vector(size_type count, value_type val);`  
  
 инициализирует контролируемая последовательность с элементами `count` каждое со значением `val`.  Он используется для заполнения контейнер с элементами, все одно и то же значение.  
  
 Конструктор:  
  
 `template<typename InIt>`  
  
 `vector(InIt first, InIt last);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности.  
  
 Конструктор:  
  
 `vector(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем.  
  
## Пример  
  
```  
// cliext_vector_construct.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::vector<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::vector<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::vector<wchar_t>::iterator it = c3.end();   
    cliext::vector<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::vector<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::vector<wchar_t> c8(%c3);   
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
 **Заголовок:**\<cliext\/vector\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [вектор](../dotnet/vector-stl-clr.md)   
 [vector::assign](../Topic/vector::assign%20\(STL-CLR\).md)   
 [vector::generic\_container](../dotnet/vector-generic-container-stl-clr.md)   
 [vector::operator\=](../dotnet/vector-operator-assign-stl-clr.md)