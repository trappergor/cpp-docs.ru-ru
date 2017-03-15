---
title: "remove_if (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::remove_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_if - функция [STL/CLR]"
ms.assetid: de501d3f-965b-4a99-b833-f6fa303fbcdc
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# remove_if (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Исключает элементы, которые удовлетворяют предикату из заданного диапазона без нарушения порядок остальных элементов и возвращая конец нового диапазона свободно указанного значения.  
  
## Синтаксис  
  
```  
template<class _FwdIt, class _Pr> inline  
    _FwdIt remove_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `remove_if` STL.  Для получения дополнительной информации см. [remove\_if](../Topic/remove_if.md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)