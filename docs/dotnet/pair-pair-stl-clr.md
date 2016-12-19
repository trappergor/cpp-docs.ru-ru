---
title: "pair::pair (STL/CLR) | Microsoft Docs"
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
  - "cliext::pair::pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair - член [STL/CLR]"
ms.assetid: 188035f3-bd37-4b46-96dd-5ceb9a16df79
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pair::pair (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект пар.  
  
## Синтаксис  
  
```  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### Параметры  
 правый  
 Пары, сохраняемых.  
  
 val1  
 Первое значение, сохраняемых.  
  
 val2  
 Во\-вторых, сохраняемых значение.  
  
## Заметки  
 Конструктор:  
  
 `pair();`  
  
 инициализирует сохраненного пары, построенными со значениями по умолчанию.  
  
 Конструктор:  
  
 `pair(pair<Value1, Value2>% right);`  
  
 инициализирует, хранящиеся в паре с `right``.`[pair::first](../dotnet/pair-first-stl-clr.md) и `right``.`[pair::second](../dotnet/pair-second-stl-clr.md).  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 инициализирует, хранящиеся в паре с `right``->`[pair::first](../dotnet/pair-first-stl-clr.md) и `right``>`[pair::second](../dotnet/pair-second-stl-clr.md).  
  
 Конструктор:  
  
 `pair(Value1 val1, Value2 val2);`  
  
 инициализирует, хранящиеся в паре с с `val1` и `val2`.  
  
## Пример  
  
```  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }  
  
```  
  
  **\[\\0, 0\]**  
**\[x, 3\]**  
**\[x, 3\]**  
**\[x, 3\]**   
## Требования  
 **Заголовок:**\<cliext\/utility\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [pair](../dotnet/pair-stl-clr.md)