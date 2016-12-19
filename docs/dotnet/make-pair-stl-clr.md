---
title: "make_pair (STL/CLR) | Microsoft Docs"
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
  - "cliext::make_pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_pair - функция [STL/CLR]"
ms.assetid: 74733f2c-97b0-4d69-b431-5ab8f0de9e3e
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# make_pair (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выполните `pair` из пары значений.  
  
## Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### Параметры  
 Value1  
 Тип первого создаватього программу\-оболочку значение.  
  
 Value2  
 Тип второго создаватього программу\-оболочку значение.  
  
 first  
 Первое значение, создающееся.  
  
 second  
 Во\-вторых, создающееся значение.  
  
## Заметки  
 Шаблонная функция возвращает `pair<``Value1``,` `Value2``>(``first``,` `second``)`.  Он используется для создания объекта `pair``<``Value1``,` `Value2``>` из пары значений.  
  
## Пример  
  
```  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
  
```  
  
  **\[x, 3\]**  
**\[y, 4\]**   
## Требования  
 **Заголовок:**\<cliext\/utility\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)