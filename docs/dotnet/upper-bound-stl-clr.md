---
title: upper_bound (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- upper_bound function [STL/CLR]
ms.assetid: a377a77b-8005-496e-85ae-b431a9b2f0b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: be87a8a91f91e3bdb4417f8ec6f0ab0c51a515cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167136"
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