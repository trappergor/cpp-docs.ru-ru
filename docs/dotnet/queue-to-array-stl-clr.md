---
title: "queue::to_array (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::to_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_array - элемент [STL/CLR]"
ms.assetid: a76a9add-659c-4dcc-a342-de7263946496
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# queue::to_array (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Копирует контролируемая последовательность в новый массив.  
  
## Синтаксис  
  
```  
cli::array<Value>^ to_array();  
```  
  
## Заметки  
 Возвращает массив, содержащий функцию\-член контролируемую последовательность.  Он используется, чтобы получить копию контролируемой последовательности в форме массива.  
  
## Пример  
  
```  
// cliext_queue_to_array.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push(L'd');   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **B C d**  
 **a b c**   
## Требования  
 **Заголовок:**\<cliext\/queue\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [queue](../Topic/queue%20\(STL-CLR\).md)