---
title: set_union (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set_union
dev_langs:
- C++
helpviewer_keywords:
- set_union function [STL/CLR]
ms.assetid: 8bafbf10-172c-47d9-88af-19b9b0c1c31f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 120113e6a94f0587cdb97d3d3c7bcff5ad7d18d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="setunion-stlclr"></a>set_union (STL/CLR)
Объединяет все элементы, входящие в хотя бы один из двух исходных упорядоченных диапазонов, в один упорядоченный диапазон назначения, где критерий порядка сортировки может быть указан бинарным предикатом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_union(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_union(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `set_union`. Дополнительные сведения см. в разделе [set_union](../standard-library/algorithm-functions.md#set_union).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)