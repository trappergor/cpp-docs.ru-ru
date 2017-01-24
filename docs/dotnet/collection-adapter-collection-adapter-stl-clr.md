---
title: "collection_adapter::collection_adapter (STL/CLR) | Microsoft Docs"
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
  - "cliext::collection_adapter"
  - "cliext::collection_adapter::collection_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collection_adapter - элемент [STL/CLR]"
ms.assetid: 7e2bb75b-d735-4135-9523-719683e06fe9
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# collection_adapter::collection_adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект адаптера.  
  
## Синтаксис  
  
```  
collection_adapter();  
collection_adapter(collection_adapter<Coll>% right);  
collection_adapter(collection_adapter<Coll>^ right);  
collection_adapter(Coll^ collection);  
```  
  
#### Параметры  
 collection  
 Дескриптор BCL, создающееся.  
  
 правый  
 Объект, подлежащих копированию.  
  
## Заметки  
 Конструктор:  
  
 `collection_adapter();`  
  
 инициализирует сохраненного дескриптора с `nullptr`.  
  
 Конструктор:  
  
 `collection_adapter(collection_adapter<Coll>% right);`  
  
 инициализирует сохраненного дескриптора с `right``.`[collection\_adapter::base](../dotnet/collection-adapter-base-stl-clr.md)`()`.  
  
 Конструктор:  
  
 `collection_adapter(collection_adapter<Coll>^ right);`  
  
 инициализирует сохраненного дескриптора с `right``->`[collection\_adapter::base](../dotnet/collection-adapter-base-stl-clr.md)`()`.  
  
 Конструктор:  
  
 `collection_adapter(Coll^ collection);`  
  
 инициализирует сохраненного дескриптора с с `collection`.  
  
## Пример  
  
```  
// cliext_collection_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
  
// construct an empty container   
    Mycoll c1;   
    System::Console::WriteLine("base() null = {0}", c1.base() == nullptr);   
  
// construct with a handle   
    Mycoll c2(%d6x);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mycoll c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mycoll c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **NULLbase\(\) \= true**  
 **x x x x x x**  
 **x x x x x x**  
 **x x x x x x**   
## Требования  
 **Заголовок:**\<cliext\/adapter\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md)   
 [collection\_adapter::operator\=](../dotnet/collection-adapter-operator-assign-stl-clr.md)