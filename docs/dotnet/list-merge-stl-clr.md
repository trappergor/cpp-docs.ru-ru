---
title: "list::merge (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::merge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "merge - член [STL/CLR]"
ms.assetid: f8e93cd3-bd08-4086-859b-08a2899cc9a6
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::merge (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объединяет две упорядоченные управляемые последовательности.  
  
## Синтаксис  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### Параметры  
 pred  
 Сравнение для пар элементов.  
  
 правый  
 Контейнер, предназначенный для слияния в.  
  
## Заметки  
 Первый функцию\-член удаляет все элементы из последовательности контролируемой `right` и вставляет их в контролируемую последовательность.  Обе ранее последовательности должны быть упорядочены `operator<` \-\- элементы не должны уменьшить значение по мере выполнения работ по любая последовательность.  В результирующей последовательности также упорядочена `operator<`.  Используется этот функции\-члена для слияния 2 последовательности, увеличение затрат " в последовательность, в которой также увеличения стоимости.  
  
 Второй функцию\-член работает аналогично во\-первых, за исключением того, что последовательности сортируются `pred` \-\- `pred``(X, Y)` должно быть значение для любого элемента `X`, соответствующий элемент `Y` в последовательности.  Он используется для слияния 2 последовательности приказанной функцией предиката или делегировать, необходимо задать.  
  
 Обе функции выполняют стабильным слияние \-\- никакая пара элементов в также исходный управляемых последовательностей не обращена в полученном контролируемой последовательности.  Кроме того, если пара элементов `X` и `Y` в полученном контролируемой последовательности имеет соответствующего упорядочение \-\- `!(X < Y) && !(X < Y)` \-\- элемент из исходной контролируемой последовательности отображается перед элементом последовательности контролируемой `right`.  
  
## Пример  
  
```  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **Ответ. C — e.**  
 **B d f**  
 **a b c d e f**  
**c2.size\(\) \= 0**  
 **E.C — a.**  
 **f e — a B C d**  
 **f e e C d — a B C.**  
**c1.size\(\) \= 0**   
## Требования  
 **Заголовок:**\<cliext\/list\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [list](../dotnet/list-stl-clr.md)   
 [list::sort](../dotnet/list-sort-stl-clr.md)   
 [list::splice](../Topic/list::splice%20\(STL-CLR\).md)