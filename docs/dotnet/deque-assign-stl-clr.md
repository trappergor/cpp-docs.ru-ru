---
title: "deque::assign (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::assign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "assign - член [STL/CLR]"
ms.assetid: 03fafdbb-6b10-4464-b3dc-0cc5cb8ac980
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# deque::assign (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Заменяет все элементы.  
  
## Синтаксис  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### Параметры  
 count  
 Число элементов, который необходимо вставить.  
  
 first  
 Начало диапазона, который необходимо вставить.  
  
 last  
 Элемент диапазона, который необходимо вставить.  
  
 правый  
 Перечисление, который необходимо вставить.  
  
 val  
 Значение элемента, который необходимо вставить.  
  
## Заметки  
 Первый функцию\-член заменяет контролируемая последовательность с повторением элементов `count` значение `val`.  Он используется для заполнения контейнер с элементами, все одно и то же значение.  
  
 Если `InIt` целочисленный тип, то второй функцию\-член работает аналогично `assign((size_type)``first``, (value_type)``last``)`.  В противном случае он заменяет контролируемая последовательность с последовательностью `[``first``,` `last``)`.  Он используется, чтобы сделать контролируемой последовательностью копию другую последовательность.  
  
 Третий функцию\-член заменяет контролируемая последовательность с последовательность — это специализированная перечислителем `right`.  Он используется, чтобы сделать контролируемой последовательностью копию последовательности две перечислителем.  
  
## Пример  
  
```  
// cliext_deque_assign.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::deque<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **x x x x x x**  
 **B**  
 **a b c**   
## Требования  
 **Заголовок:**\<cliext\/deque\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [deque](../dotnet/deque-stl-clr.md)   
 [operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)