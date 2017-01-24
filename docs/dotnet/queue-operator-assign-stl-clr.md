---
title: "queue::operator= (STL/CLR) | Microsoft Docs"
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
  - "cliext::queue::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= - член [STL/CLR]"
ms.assetid: 826c335a-5680-498c-b57d-e7bc93a914be
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queue::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Заменяет контролируемая последовательность.  
  
## Синтаксис  
  
```  
queue <Value, Container>% operator=(queue <Value, Container>% right);  
```  
  
#### Параметры  
 правый  
 Адаптер контейнера, которые нужно скопировать.  
  
## Заметки  
 Член оператор копирует `right` к объекту, а затем возвращает `*this`.  Он используется, чтобы заменить контролируемая последовательность копией контролируемой последовательности в `right`.  
  
## Пример  
  
```  
// cliext_queue_operator_as.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**   
## Требования  
 **Заголовок:**\<cliext\/queue\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [queue](../Topic/queue%20\(STL-CLR\).md)   
 [queue::assign](../dotnet/queue-assign-stl-clr.md)