---
title: "max (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::max"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "максимальная функция [STL/CLR]"
ms.assetid: bf51aedc-b7a0-4b6c-a76e-fdbc4af042fa
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# max (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Сравнивает 2 объекта и возвращает большее 2, где критерий упорядочивания может быть указан бинарным предикатом.  
  
## Синтаксис  
  
```  
template<class _Ty> inline  
    const _Ty max(const _Ty% _Left, const _Ty% _Right);  
template<class _Ty, class _Pr> inline  
    const _Ty max(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `max` STL.  Для получения дополнительной информации см. [max](../Topic/max.md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)