---
title: "list::insert (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert - член [STL/CLR]"
ms.assetid: 399ed30f-6b76-41a8-b180-6070e3ca1c68
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Добавляет элементы в указанной позиции.  
  
## Синтаксис  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
 , где  
 , Где в контейнере вставить ранее.  
  
## Заметки  
 Каждый из функции\-члены вставки, перед элементом указал в `where` в контролируемой последовательности, определенная последовательность оставшимися операндами.  
  
 Первый функцию\-член вставляет элемент со значением `val` и возвращает итератор, обозначает вновь добавленного элемента.  Он используется для вставки одного элемента перед место обозначенным итератором.  
  
 Второй функцию\-член вставляет повторение элементов `count` значение `val`.  Он используется для вставки ноль или более соседние элементы, все копии одного и того же значения.  
  
 Если `InIt` целочисленный тип, третий функцию\-член работает аналогично `insert(``where``, (size_type)``first``, (value_type)``last``)`.  В противном случае он представляет последовательность `[``first``,` `last``)`.  Он используется для вставки ноль или более соседние элементы, скопированных из другой последовательности.  
  
 Четвертый функцию\-член вставляет последовательность обозначенную `right`.  Он используется для вставки последовательность описанную перечислителем.  
  
 Вставка одного элемента, число копий элемента линейное количества элементов между точкой вставки и более точно концом последовательности. \(При внедрении один или несколько элементов в какой\-либо конец последовательности, никакие копии элемента не возникает\). Если `InIt` итератор ввода, третий функцию\-член эффективно выполняет вставку одну для каждого элемента в последовательности.  В противном случае при внедрении элементов `N`, число копий линейное элемента в `N` плюс количество элементов между точкой вставки и более точно концом последовательности.  
  
## Пример  
  
```  
// cliext_list_insert.cpp   
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
  
// insert a single value using iterator   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using index   
    it = c2.begin();   
    ++it, ++it, ++it;   
    c2.insert(it, L'z');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **a b c**  
**insert\(begin\(\)\+1, L'x\) \= x**  
 **x B C.**  
 **y y**  
 **y x y B**  
 **x y B C — x y B**   
## Требования  
 **Заголовок:**\<cliext\/list\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [list](../dotnet/list-stl-clr.md)   
 [list::assign](../dotnet/list-assign-stl-clr.md)