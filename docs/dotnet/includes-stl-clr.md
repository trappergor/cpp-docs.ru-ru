---
title: "includes (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::includes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "includes - функция [STL/CLR]"
ms.assetid: 566307f4-92e0-4acc-ba49-caa48f3ec744
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# includes (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Тесты, содержит ли один сортируемый диапазон весь диапазон содержат элементы, во второй упорядоченный, где критерии упорядочение или эквивалентности между элементами можно определить бинарным предикатом.  
  
## Синтаксис  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `includes` STL.  Для получения дополнительной информации см. [includes](../Topic/includes.md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)