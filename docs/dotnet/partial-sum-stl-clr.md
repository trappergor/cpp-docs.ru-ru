---
title: "partial_sum (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::partial_sum
dev_langs:
- C++
helpviewer_keywords:
- partial_sum function [STL/CLR]
ms.assetid: 845badae-8519-4ac8-9ea7-2b921bac7c51
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7200fbf4adb7866125cfd8956b7b35ad5d5a2657
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="partialsum-stlclr"></a>partial_sum (STL/CLR)
Вычисляет ряд сумм в диапазоне ввода с первого элемента и до `i`элемент th и сохраняет результат каждой такой суммы в `i`-ый элемент диапазон назначения или вычисляет результат обобщенной процедуры, где операции суммы заменяется на другой указанной бинарной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как числовая функция стандартной библиотеки C++ `partial_sum`. Дополнительные сведения см. в разделе [partial_sum](../standard-library/numeric-functions.md#partial_sum).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/numeric >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)