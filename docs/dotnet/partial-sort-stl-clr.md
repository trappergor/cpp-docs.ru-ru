---
title: partial_sort (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::partial_sort
dev_langs:
- C++
helpviewer_keywords:
- partial_sort function [STL/CLR]
ms.assetid: 5a73b275-aef0-4bda-8ae3-7c1196fe49c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fad07bb56e4e6a6fa85a6fb25b98c114df72e4bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33159981"
---
# <a name="partialsort-stlclr"></a>partial_sort (STL/CLR)
Упорядочивает указанное число меньших элементов в диапазоне в не нисходящий порядок или согласно критерию упорядочивания, заданному бинарным предикатом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _RanIt> inline  
    void partial_sort(_RanIt _First, _RanIt _Mid, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void partial_sort(_RanIt _First, _RanIt _Mid, _RanIt _Last,  
        _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `partial_sort`. Дополнительные сведения см. в разделе [partial_sort](../standard-library/algorithm-functions.md#partial_sort).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)