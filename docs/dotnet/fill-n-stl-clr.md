---
title: "fill_n (STL/CLR) | Microsoft Docs"
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
  - "cliext::fill_n"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fill_n - функция"
ms.assetid: bb9f2f71-ba1d-44ec-8b47-6ece149dd6b8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# fill_n (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Присваивает новое значение указанному количеству элементов в диапазоне, который начинается с определенного элемента.  
  
## Синтаксис  
  
```  
template<class _OutIt, class _Diff, class _Ty> inline  
    void fill_n(_OutIt _First, _Diff _Count, const _Ty% _Val);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `fill_n` STL.  Для получения дополнительной информации см. [fill\_n](../Topic/fill_n.md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)