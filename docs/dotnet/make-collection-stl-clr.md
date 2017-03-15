---
title: "make_collection (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::make_collection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_collection - функция [STL/CLR]"
ms.assetid: c25fb0cb-ebd8-4198-a565-bad28d32ee19
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# make_collection (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выполните `range_adapter` из пары итератора.  
  
## Синтаксис  
  
```  
template<typename Iter>  
    range_adapter<Iter> make_collection(Iter first, Iter last);  
```  
  
#### Параметры  
 Iter  
 Тип созданы программу\-оболочку итераторов.  
  
 first  
 Первый итератор, создающееся.  
  
 last  
 Второй итератор, создающееся.  
  
## Заметки  
 Шаблонная функция возвращает `gcnew range_adapter<Iter>(``first``,` `last``)`.  Он используется для создания объекта `range_adapter``<Iter>` из пары итераторов.  
  
## Пример  
  
```  
// cliext_make_collection.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in d1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Collections::ICollection^ p1 =   
        cliext::make_collection(d1.begin(), d1.end());   
    System::Console::WriteLine("Count = {0}", p1->Count);   
    System::Console::WriteLine("IsSynchronized = {0}",   
        p1->IsSynchronized);   
    System::Console::WriteLine("SyncRoot not nullptr = {0}",   
        p1->SyncRoot != nullptr);   
  
// copy the sequence   
    cli::array<System::Object^>^ a1 = gcnew cli::array<System::Object^>(5);   
  
    a1[0] = L'|';   
    p1->CopyTo(a1, 1);   
    a1[4] = L'|';   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **a b c**  
**Количество \= 3**  
**IsSynchronized \= false**  
**Nullptr SyncRoot не \= true**  
 **&#124; B C. &#124;**   
## Требования  
 **Заголовок:**\<cliext\/adapter\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)