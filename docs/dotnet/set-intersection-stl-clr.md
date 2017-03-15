---
title: "set_intersection (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set_intersection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set_intersection - функция [STL/CLR]"
ms.assetid: 8a799b20-55a5-4fba-a9c1-a48597cbdae6
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# set_intersection (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Соединяет все элементы, которые принадлежат обоим отсортированных диапазоны источника в один, упорядоченный диапазон назначения, где критерий упорядочивания может быть указан бинарным предикатом.  
  
## Синтаксис  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_intersection(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `set_intersection` STL.  Для получения дополнительной информации см. [set\_intersection](../Topic/set_intersection.md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)