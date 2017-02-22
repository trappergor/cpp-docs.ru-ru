---
title: "multimap::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase - член [STL/CLR]"
ms.assetid: 94623cfc-4464-44a6-afd4-90a36828ac2b
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multimap::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Удаляет элементы в указанных положениях.  
  
## Синтаксис  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### Параметры  
 first  
 Начало диапазона, чтобы привести к удалению.  
  
 key  
 Значение ключа, чтобы привести к удалению.  
  
 last  
 Элемент диапазона, чтобы привести к удалению.  
  
 , где  
 Элемент, который необходимо привести к удалению.  
  
## Заметки  
 Первый функцию\-член удаляет элемент контролируемой последовательности, указанное в `where` и возвращает первый элемент указывает итератор, оставшиеся за удаленным элементом, или [multimap::end](../dotnet/multimap-end-stl-clr.md)`()`, если такой элемент не существует.  Он используется для удаления одного элемента.  
  
 Второй функцию\-член удаляет элементы контролируемой последовательности в диапазоне `[``first``,` `last``)` и возвращает первый элемент указывает итератор, оставшиеся за всеми удаленными элементами, или `end()`, если такой элемент не существует.  Он используется для удаления ноль или более соседние элементы.  
  
 Третий функцию\-член удаляет любой элемент контролируемой последовательности ключ которой имеет соответствующий заказ на `key` и возвращается число удаленных элементов.  Он используется для удаления и подсчитать все элементы, соответствующие указанному ключу.  
  
 Каждое erase элемента имеет время пропорциональное в логарифму числа элементов в контролируемой последовательности.  
  
## Пример  
  
```  
// cliext_multimap_erase.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    cliext::multimap<wchar_t, int> c1;   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'a', 1));   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'b', 2));   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (cliext::multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    cliext::multimap<wchar_t, int>::iterator it =   
        c1.erase(c1.begin());   
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",   
        it->first, it->second);   
  
// add elements and display " b c d e"   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'd', 4));   
    c1.insert(cliext::multimap<wchar_t, int>::make_value(L'e', 5));   
    for each (cliext::multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase all but end   
    it = c1.end();   
    it = c1.erase(c1.begin(), --it);   
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",   
        it->first, it->second);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// erase end   
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));   
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[BC — 3\]**  
**erase\(begin\(\)\) \= \[B 2\]**  
 **\[2\] B C \[3\] \[4\] \[de 5\]**  
**erase\(begin\(\), \-1\) \= \[ end\(\)e 5\]**  
**size\(\) \= 1**  
**erase \(L'x\) \= 0**  
**erase \(L'e\) \= 1**   
## Требования  
 **Заголовок:**\<cliext\/map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::clear](../Topic/multimap::clear%20\(STL-CLR\).md)