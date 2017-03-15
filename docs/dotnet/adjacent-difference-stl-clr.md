---
title: "adjacent_difference (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::adjacent_difference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adjacent_difference - функция"
ms.assetid: 2b462e2e-b8f2-4b2e-9b87-5f688d8da9f4
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# adjacent_difference (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вычисляет последовательные различия между каждым элементом и его предшественником в диапазоне ввода и выводит результаты в качестве назначения или вычисляет результат обобщенной процедуры, операция различия заменяется другим, определенной бинарной операции.  
  
## Синтаксис  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `adjacent_difference` STL числовые.  Для получения дополнительной информации см. [adjacent\_difference](../Topic/adjacent_difference.md).  
  
## Требования  
 **Заголовок:**\<cliext\/numeric\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [числовой](../dotnet/numeric-stl-clr.md)