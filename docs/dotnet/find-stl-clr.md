---
title: "find (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find - функция [STL/CLR]"
ms.assetid: 88391e24-1239-4087-b1c2-96efba0337c1
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# find (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Находит позицию первого вхождения элемента в диапазон с заданным значением.  
  
## Синтаксис  
  
```  
template<class _InIt, class _Ty> inline  
    _InIt find(_InIt _First, _InIt _Last, const _Ty% _Val);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `find` STL.  Для получения дополнительной информации см. [find](../Topic/find%20\(STL\).md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)