---
title: Merge (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::merge
dev_langs:
- C++
helpviewer_keywords:
- merge function [STL/CLR]
ms.assetid: e42d3396-63a4-438a-964d-83e90405102e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 09f9cc8d81eb4862607d2382f7d3d2ac033cf111
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="merge-stlclr"></a>merge (STL/CLR)
Объединяет все элементы из двух исходных упорядоченных диапазонов в один упорядоченный диапазон назначения, где критерий порядка сортировки может быть указан бинарным предикатом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt merge(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt merge(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `merge`. Дополнительные сведения см. в разделе [слияния](../standard-library/algorithm-functions.md#merge).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)