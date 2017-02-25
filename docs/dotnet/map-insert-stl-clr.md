---
title: "map::insert (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert - член [STL/CLR]"
ms.assetid: 599c702e-7db0-45b8-8247-4ff041a3639c
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# map::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Добавляет элементы.  
  
## Синтаксис  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
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
  
 Первый функцию\-член стремится вставить элемент со значением `val` и возвращения пара значений `X`.  Если `X.second` выполняется, `X.first` обозначает вновь добавленного элемента; в противном случае `X.first` обозначает элемент с соответствующей приказывающ то уже существует и не новый элемент не будет.  Он используется для вставки одного элемента.  
  
 Второй функцию\-член вставляет элемент со значением `val`, с помощью `where` как подсказка \(повысить производительность\) и возвращает итератор, обозначает вновь добавленного элемента.  Он используется для вставки один элемент, который может быть рядом с элементом известно.  
  
 Третий функцию\-член вставляет последовательность `[``first``,` `last``)`.  Он используется для вставки ноль или более элементов скопированных из другой последовательности.  
  
 Четвертый функцию\-член вставляет последовательность обозначенную `right`.  Он используется для вставки последовательность описанную перечислителем.  
  
 Каждая вставка элемента требует времени, пропорциональное логарифму числа элементов в контролируемой последовательности.  Вставка может произойти в амортизированном постоянно времени, заданную подсказку, которая обозначает элемент рядом с точкой вставки.  
  
## Пример  
  
```  
// cliext_map_insert.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef Mymap::pair_iter_bool Pairib;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
// insert a single value, success and failure   
    Pairib pair1 = c1.insert(Mymap::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    pair1 = c1.insert(Mymap::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    Mymap::iterator it =   
        c1.insert(c1.begin(), Mymap::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymap c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymap c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Mymap::value_type>^)%c1);   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[BC — 3\]**  
**вставка L'x \(\[24\] \= \[\[\)значение true x24\]\]**  
**вставка L'b \(\[2\] \= \[\[\)2 B false\]\]**  
 **\[1\] \[2\] \[B C \[3\]x24\]**  
**insert\(begin\(\), L'y \[25\] \= \[\)y 25\]**  
 **\[1\] \[2\] \[B C\] \[3\] \[x24y 25\]**  
 **\[1\] \[2\] \[B C \[3\]x24\]**  
 **\[1\] \[2\] \[B C\] \[3\] \[x24y 25\]**   
## Требования  
 **Заголовок:**\<cliext\/map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [map](../dotnet/map-stl-clr.md)