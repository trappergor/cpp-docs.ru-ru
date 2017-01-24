---
title: "find_first_of (STL/CLR) | Microsoft Docs"
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
  - "cliext::find_first_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find_first_of - функция [STL/CLR]"
ms.assetid: d559bad4-fc12-4201-af49-db0e7eec48e8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# find_first_of (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Поиск первого вхождения любого из следующих значений в полигон или для первого вхождения любого из следующих элементов, соответствующих в некотором смысле определенные бинарным предикату в указанный набор элементов.  
  
## Синтаксис  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2);  
template<class _FwdIt1, class _FwdIt2, class _Pr> inline  
    _FwdIt1 find_first_of(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `find_first_of` STL.  Для получения дополнительной информации см. [find\_first\_of](../Topic/find_first_of.md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)