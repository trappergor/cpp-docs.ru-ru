---
title: "next_permutation (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::next_permutation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "next_permutation - функция [STL/CLR]"
ms.assetid: e36e821f-4b8d-461b-8074-69cd0175ccec
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# next_permutation (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Порядок элементов в диапазоне, чтобы исходный порядок будет заменен лексикографически следующим большим пермутированием, если оно существует, где смысл следующего мая был определен с бинарным предикатом.  
  
## Синтаксис  
  
```  
template<class _BidIt> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `next_permutation` STL.  Для получения дополнительной информации см. [next\_permutation](../Topic/next_permutation.md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)