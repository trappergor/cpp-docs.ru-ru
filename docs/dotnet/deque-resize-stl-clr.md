---
title: "deque::resize (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resize - член [STL/CLR]"
ms.assetid: c83f3c57-38b3-4706-a124-59bafbf88484
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# deque::resize (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Изменяет количество элементов.  
  
## Синтаксис  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### Параметры  
 new\_size  
 Новый размер контролируемой последовательности.  
  
 val  
 Значение элемента заполнения.  
  
## Заметки  
 Функции\-члены предоставляют как [deque::size](../Topic/deque::size%20\(STL-CLR\).md)`()` впредь возвращает `new_size`.  Если он должен выполнить контролируемую последовательность более длинным, первый функцию\-член добавляет элементы со значением `value_type()`, а во втором функцию\-член добавляет элементы со значением `val`.  Чтобы сделать контролируемую последовательность более коротким, оба функции\-члена эффективно стирают последние время [deque::size](../Topic/deque::size%20\(STL-CLR\).md)`() -` `new_size` элемента.  Он используется для обеспечения контролируемая последовательность имеет размер `new_size` или фильтрацией по ролям или заполнением текущей контролируемая последовательность.  
  
## Пример  
  
```  
// cliext_deque_resize.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0 0**  
**size\(\) \= 0**  
 **x x x x x**   
## Требования  
 **Заголовок:**\<cliext\/deque\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::clear](../dotnet/deque-clear-stl-clr.md)   
 [deque::erase](../Topic/deque::erase%20\(STL-CLR\).md)   
 [deque::insert](../dotnet/deque-insert-stl-clr.md)