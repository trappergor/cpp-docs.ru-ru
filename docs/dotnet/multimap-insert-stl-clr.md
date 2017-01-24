---
title: "multimap::insert (STL/CLR) | Microsoft Docs"
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
  - "cliext::multimap::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert - член [STL/CLR]"
ms.assetid: 98922ea1-c7ed-4c53-8834-8a0470b11c9e
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multimap::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Добавляет элементы.  
  
## Синтаксис  
  
```  
iterator insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### Параметры  
 first  
 Начало диапазона, который необходимо вставить.  
  
 last  
 Элемент диапазона, который необходимо вставить.  
  
 правый  
 Перечисление, который необходимо вставить.  
  
 val  
 Значение ключа, который необходимо вставить.  
  
 , где  
 , Где в контейнере вставки \(подсказка только\).  
  
## Заметки  
 Каждый из функции\-члены содержит определенную последовательность оставшимися операндами.  
  
 Первый функцию\-член вставляет элемент со значением `val` и возвращает итератор, обозначает вновь добавленного элемента.  Он используется для вставки одного элемента.  
  
 Второй функцию\-член вставляет элемент со значением `val`, с помощью `where` как подсказка \(повысить производительность\) и возвращает итератор, обозначает вновь добавленного элемента.  Он используется для вставки один элемент, который может быть рядом с элементом известно.  
  
 Третий функцию\-член вставляет последовательность `[``first``,` `last``)`.  Он используется для вставки ноль или более элементов скопированных из другой последовательности.  
  
 Четвертый функцию\-член вставляет последовательность обозначенную `right`.  Он используется для вставки последовательность описанную перечислителем.  
  
 Каждая вставка элемента требует времени, пропорциональное логарифму числа элементов в контролируемой последовательности.  Вставка может произойти в амортизированном постоянно времени, заданную подсказку, которая обозначает элемент рядом с точкой вставки.  
  
## Пример  
  
```  
// cliext_multimap_insert.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Mymultimap::iterator it =   
        c1.insert(Mymultimap::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}]",   
        it->first, it->second);   
  
    it = c1.insert(Mymultimap::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}]",   
        it->first, it->second);   
  
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    it = c1.insert(c1.begin(), Mymultimap::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymultimap c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymultimap c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Mymultimap::value_type>^)%c1);   
    for each (Mymultimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[BC — 3\]**  
**вставка L'x \(\[24\] \= \[\)x24\]**  
**вставка L'b \(\[2\] \= \[\)B 2\]**  
 **\[1\] \[2\] B B \[2\] \[3\] \[C.x24\]**  
**insert\(begin\(\), L'y \[25\] \= \[\)y 25\]**  
 **\[1\] B \[2\] \[2\] \[B C\] \[3\] \[x24y 25\]**  
 **\[1\] \[2\] B B \[2\] \[3\] \[C.x24\]**  
 **\[1\] B \[2\] \[2\] \[B C\] \[3\] \[x24y 25\]**   
## Требования  
 **Заголовок:**\<cliext\/map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [multimap](../dotnet/multimap-stl-clr.md)