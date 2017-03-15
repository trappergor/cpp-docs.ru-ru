---
title: "list::unique (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::unique"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique - член [STL/CLR]"
ms.assetid: c3a29e4e-0ec1-4472-b050-7a9511037132
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::unique (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Удаляет смежные элементы, которые прошли заданный тест.  
  
## Синтаксис  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### Параметры  
 pred  
 Сравнение для пар элементов.  
  
## Заметки  
 Первый функцию\-член удаляет из контролируемой последовательности \(удаляются\) каждый элемент, который сравнивает равно его элементу: \-\- если элемент `X` предшествующего элемента `Y` и `X == Y`, функцию\-член удаляет `Y`.  Он используется, чтобы удалить все, кроме одна копия каждого subsequence соседних элементов, которые сравнивают равенство.  Обратите внимание, что если контролируемая последовательность упорядочена, например путем вызова [list::sort](../dotnet/list-sort-stl-clr.md)`()`, функцию\-член, отображается только элементы с уникальными значениями. \(Это имя\).  
  
 Второй функцию\-член работает аналогично во\-первых, за исключением того, что он удаляет каждый элемент `Y` после элемента `X`, для которого `pred``(X, Y)`.  Он используется, чтобы удалить все, кроме одна копия каждого subsequence соседних элементов, которые удовлетворяют функции предиката\) или делегируете, необходимо задать.  Обратите внимание, что если контролируемая последовательность упорядочена, например путем вызова `sort(``pred``)`, функцию\-член, отображается только те элементы, которые не имеют соответствующего упорядочение со всеми другими элементами.  
  
## Пример  
  
```  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a a b c**  
 **a b c**  
 **a**   
## Требования  
 **Заголовок:**\<cliext\/list\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [list](../dotnet/list-stl-clr.md)   
 [list::remove](../dotnet/list-remove-stl-clr.md)   
 [list::remove\_if](../dotnet/list-remove-if-stl-clr.md)   
 [list::sort](../dotnet/list-sort-stl-clr.md)