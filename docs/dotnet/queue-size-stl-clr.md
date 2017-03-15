---
title: "queue::size (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size - член [STL/CLR]"
ms.assetid: 864510ef-5a00-4377-b286-1e73f237e359
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# queue::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Подсчитывает количество элементов.  
  
## Синтаксис  
  
```  
size_type size();  
```  
  
## Заметки  
 Возвращает длину функцию\-член контролируемой последовательности.  Он используется для определения числа элементов в контролируемой последовательности.  Если требуется заботите около, имеет ли последовательность ненулевое размер см. в разделе [queue::empty](../Topic/queue::empty%20\(STL-CLR\).md)`()`.  
  
## Пример  
  
```  
// cliext_queue_size.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**size\(\) \= 3, начиная с 3**  
**size\(\) \= 2 после извлечения**  
**size\(\) \= 4 после добавления 2**   
## Требования  
 **Заголовок:**\<cliext\/queue\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [queue](../Topic/queue%20\(STL-CLR\).md)   
 [queue::empty](../Topic/queue::empty%20\(STL-CLR\).md)