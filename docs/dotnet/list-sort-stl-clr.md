---
title: "list::sort (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::sort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sort - член [STL/CLR]"
ms.assetid: f811d5f4-a19e-4194-8765-1e68097c52f0
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# list::sort (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Упорядочивает управляемую последовательность.  
  
## Синтаксис  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### Параметры  
 pred  
 Сравнение для пар элементов.  
  
## Заметки  
 Первый функцию\-член выполняет переупорядочивание элементов в контролируемой последовательности, чтобы они были упорядочены `operator<` \-\- элементы не уменьшает значение по мере выполнения работ с помощью последовательности.  Используется этот функции\-члена для сортировки увеличивается последовательность в порядке.  
  
 Второй функцию\-член работает аналогично во\-первых, за исключением того, что последовательность упорядочена `pred` \-\- `pred``(X, Y)` значение для любого элемента `X`, соответствующий элемент `Y` в возникающей последовательности.  Он используется для сортировки последовательность в порядке, который задается функцией или делегатом предиката.  
  
 Обе функции выполняют сортировку стабилизированную \-\- никакая пара элементов в исходном контролируемой последовательности не обращена в полученном контролируемой последовательности.  
  
## Пример  
  
```  
// cliext_list_sort.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a B C.**  
 **a b c**   
## Требования  
 **Заголовок:**\<cliext\/list\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [list](../dotnet/list-stl-clr.md)   
 [list::merge](../dotnet/list-merge-stl-clr.md)   
 [list::reverse](../dotnet/list-reverse-stl-clr.md)   
 [list::splice](../Topic/list::splice%20\(STL-CLR\).md)   
 [list::unique](../dotnet/list-unique-stl-clr.md)