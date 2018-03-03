---
title: "upper_bound (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- upper_bound function [STL/CLR]
ms.assetid: a377a77b-8005-496e-85ae-b431a9b2f0b9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f71f58990d413cea1f34cb1bcf40e6187a9f9707
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="upperbound-stlclr"></a>upper_bound (STL/CLR)
Находит позицию первого элемента в упорядоченном диапазоне, который имеет значение больше указанного значения, где критерий упорядочивания может быть задан бинарным предикатом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _FwdIt, class _Ty> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `upper_bound`. Дополнительные сведения см. в разделе [upper_bound](../standard-library/algorithm-functions.md#upper_bound).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)