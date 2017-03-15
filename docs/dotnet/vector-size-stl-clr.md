---
title: "vector::size (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size - член [STL/CLR]"
ms.assetid: 3d2a156e-5871-4441-9307-21a20cd1430f
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# vector::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Подсчитывает количество элементов.  
  
## Синтаксис  
  
```  
size_type size();  
```  
  
## Заметки  
 Возвращает длину функцию\-член контролируемой последовательности.  Он используется для определения числа элементов в контролируемой последовательности.  Если требуется заботите около, имеет ли последовательность ненулевое размер см. в разделе [vector::empty](../Topic/vector::empty%20\(STL-CLR\).md)`()`.  
  
## Пример  
  
```  
// cliext_vector_size.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**size\(\) \= 3, начиная с 3**  
**size\(\) \= 0 после очистки**  
**size\(\) \= 2 после добавления 2**   
## Требования  
 **Заголовок:**\<cliext\/vector\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [вектор](../dotnet/vector-stl-clr.md)   
 [vector::empty](../Topic/vector::empty%20\(STL-CLR\).md)