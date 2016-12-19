---
title: "stack::size (STL/CLR) | Microsoft Docs"
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
  - "cliext::stack::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size - член [STL/CLR]"
ms.assetid: 6113e649-a4f9-4021-8131-34cee4bc8ca0
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stack::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Подсчитывает количество элементов.  
  
## Синтаксис  
  
```  
size_type size();  
```  
  
## Заметки  
 Возвращает длину функцию\-член контролируемой последовательности.  Он используется для определения числа элементов в контролируемой последовательности.  Если требуется заботите около, имеет ли последовательность ненулевое размер см. в разделе [stack::empty](../dotnet/stack-empty-stl-clr.md)`()`.  
  
## Пример  
  
```  
// cliext_stack_size.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
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
 **Заголовок:**\<cliext\/stack\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [стек](../dotnet/stack-stl-clr.md)   
 [stack::empty](../dotnet/stack-empty-stl-clr.md)