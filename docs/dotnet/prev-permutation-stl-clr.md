---
title: "prev_permutation (STL/CLR) | Microsoft Docs"
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
  - "cliext::prev_permutation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "prev_permutation - функция [STL/CLR]"
ms.assetid: 5294dbe5-1b5f-4369-a764-067dff86d1e8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# prev_permutation (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Порядок элементов в диапазоне, чтобы исходный порядок будет заменен лексикографически следующим большим пермутированием, если оно существует, где смысл следующего мая был определен с бинарным предикатом.  
  
## Синтаксис  
  
```  
template<class _BidIt> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `prev_permutation` STL.  Для получения дополнительной информации см. [prev\_permutation](../Topic/prev_permutation.md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)