---
title: "map::map (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "map - элемент [STL/CLR]"
ms.assetid: c91f699a-4742-4859-b2b3-c2a01a750bea
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# map::map (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект контейнера.  
  
## Синтаксис  
  
```  
map();  
explicit map(key_compare^ pred);  
map(map<Key, Mapped>% right);  
map(map<Key, Mapped>^ right);  
template<typename InIter>  
    mapmap(InIter first, InIter last);  
template<typename InIter>  
    map(InIter first, InIter last,  
        key_compare^ pred);  
map(System::Collections::Generic::IEnumerable<GValue>^ right);  
map(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### Параметры  
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
  
 `map();`  
  
 инициализирует контролируемая последовательность без элементов с предикатом `key_compare()` по умолчанию порядок.  Он используется, чтобы указать пустую последовательность, начальную контролируемую с предикатом по умолчанию порядок.  
  
 Конструктор:  
  
 `explicit map(key_compare^ pred);`  
  
 инициализирует контролируемая последовательность без элементов, порядок с предикатом `pred`.  Он используется для определения начальную контролируемую пустую последовательность, указанным при упорядочивании предикатом.  
  
 Конструктор:  
  
 `map(map<Key, Mapped>% right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``.`[map::begin](../dotnet/map-begin-stl-clr.md)`(),` `right``.`[map::end](../dotnet/map-end-stl-clr.md)`())` с предикатом по умолчанию порядок.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `right` сопоставления с предикатом по умолчанию порядок.  
  
 Конструктор:  
  
 `map(map<Key, Mapped>^ right);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``right``->`[map::begin](../dotnet/map-begin-stl-clr.md)`(),` `right``->`[map::end](../dotnet/map-end-stl-clr.md)`())` с предикатом по умолчанию порядок.  Он используется, чтобы определить домашнюю контролируемую последовательность, копию последовательности контролируемой объектом `right` сопоставления с предикатом по умолчанию порядок.  
  
 Конструктор:  
  
 `template<typename InIter>`  
  
 `map(InIter first, InIter last);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)` с предикатом по умолчанию порядок.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности, с предикатом по умолчанию порядок.  
  
 Конструктор:  
  
 `template<typename InIter>`  
  
 `map(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 инициализирует контролируемая последовательность с последовательностью `[``first``,` `last``)`, порядок с предикатом `pred`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности, указанным при упорядочивании предикатом.  
  
 Конструктор:  
  
 `map(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right` с предикатом по умолчанию порядок.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем с предикатом по умолчанию порядок.  
  
 Конструктор:  
  
 `map(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 инициализирует контролируемая последовательность с последовательность — это специализированная перечислителем `right`, порядок с предикатом `pred`.  Он используется, чтобы сделать контролируемой последовательностью копии другой последовательности две перечислителем, указанным при упорядочивании предикатом.  
  
## Пример  
  
```  
// cliext_map_construct.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
// construct an empty container   
    Mymap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymap c3(c1.begin(), c1.end());   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Mymap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymap::value_type>^)%c3);   
    for each (Mymap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Mymap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymap c7(c4);   
    for each (Mymap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mymap c8(%c3);   
    for each (Mymap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **\[1\] \[2\] \[BC — 3\]**  
**size\(\) \= 0**  
 **C \[3\] \[2\] \[B1\]**  
 **\[1\] \[2\] \[BC — 3\]**  
 **C \[3\] \[2\] \[B1\]**  
 **\[1\] \[2\] \[BC — 3\]**  
 **C \[3\] \[2\] \[B1\]**  
 **C \[3\] \[2\] \[B1\]**  
 **\[1\] \[2\] \[BC — 3\]**   
## Требования  
 **Заголовок:**\<cliext\/map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [map](../dotnet/map-stl-clr.md)   
 [map::generic\_container](../Topic/map::generic_container%20\(STL-CLR\).md)   
 [map::operator\=](../dotnet/map-operator-assign-stl-clr.md)