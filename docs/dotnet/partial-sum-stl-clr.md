---
title: "partial_sum (STL/CLR) | Microsoft Docs"
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
  - "cliext::partial_sum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "partial_sum - функция [STL/CLR]"
ms.assetid: 845badae-8519-4ac8-9ea7-2b921bac7c51
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# partial_sum (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вычисляет ряд сумм в диапазоне ввода из первого элемента через элемент th `i` и сохраняет результат каждой такой суммы в элементе th `i` диапазона назначения или вычисляет результат обобщенной процедуры, операция суммы заменена другой определенной бинарной операцией.  
  
## Синтаксис  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `partial_sum` STL числовые.  Для получения дополнительной информации см. [partial\_sum](../Topic/partial_sum.md).  
  
## Требования  
 **Заголовок:**\<cliext\/numeric\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [числовой](../dotnet/numeric-stl-clr.md)