---
title: "accumulate (STL/CLR) | Microsoft Docs"
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
  - "cliext::accumulate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accumulate - функция [STL/CLR]"
ms.assetid: b80e1ef1-1858-4c1d-817b-c42ad1f17a2f
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# accumulate (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вычисляет сумму всех элементов в заданном диапазоне, включая некоторые начальное значение путем группирования последовательные частично суммы или вычисляет результат последовательных частично результатов аналогично полученных от использования определенной бинарной операции, отличный от суммы.  
  
## Синтаксис  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `accumulate` STL числовые.  Для получения дополнительной информации см. [accumulate](../Topic/accumulate.md).  
  
## Требования  
 **Заголовок:**\<cliext\/numeric\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [числовой](../dotnet/numeric-stl-clr.md)