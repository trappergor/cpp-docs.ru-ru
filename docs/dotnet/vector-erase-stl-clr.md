---
title: "vector::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase - член [STL/CLR]"
ms.assetid: 624905eb-83c0-499b-a07a-c10aebd7acc3
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# vector::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Удаляет элементы в указанных положениях.  
  
## Синтаксис  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### Параметры  
 first  
 Начало диапазона, чтобы привести к удалению.  
  
 last  
 Элемент диапазона, чтобы привести к удалению.  
  
 , где  
 Элемент, который необходимо привести к удалению.  
  
## Заметки  
 Первый функцию\-член удаляет элемент контролируемой последовательности, указанное в `where`.  Он используется для удаления одного элемента.  
  
 Второй функцию\-член удаляет элементы контролируемой последовательности в диапазоне `[``first``,` `last``)`.  Он используется для удаления ноль или более соседние элементы.  
  
 Оба функции\-члена возвращают итератор, обозначает первый элемент оставшиеся за всеми удаленными элементами или [vector::end](../dotnet/vector-end-stl-clr.md)`()`, если такой элемент не существует.  
  
 Стирая элементы, число копий элемента линейное количества элементов между концом стирания и более точно концом последовательности. \(Стирая один или несколько элементов в любом конце последовательности, никакие копии элемента не возникает\).  
  
## Пример  
  
```  
// cliext_vector_erase.cpp   
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
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::vector<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **a b c**  
**erase\(begin\(\)\) \= B**  
 **B C, d, e**  
**erase\(begin\(\), end\(\)\-1\) \= e**  
**size\(\) \= 1**   
## Требования  
 **Заголовок:**\<cliext\/vector\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [вектор](../dotnet/vector-stl-clr.md)   
 [vector::clear](../dotnet/vector-clear-stl-clr.md)