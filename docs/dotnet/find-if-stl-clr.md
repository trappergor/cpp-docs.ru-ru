---
title: "find_if (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::find_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find_if - функция [STL/CLR]"
ms.assetid: fd0db2be-a1e1-417e-8eea-653b08c9577e
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# find_if (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Находит позицию первого вхождения элемента в диапазон, который удовлетворяет указанному условию.  
  
## Синтаксис  
  
```  
template<class _InIt, class _Pr> inline  
    _InIt find_if(_InIt _First, _InIt _Last, _Pr _Pred);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `find_if` STL.  Для получения дополнительной информации см. [find\_if](../Topic/find_if.md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)