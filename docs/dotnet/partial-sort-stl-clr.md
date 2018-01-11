---
title: "partial_sort (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::partial_sort
dev_langs: C++
helpviewer_keywords: partial_sort function [STL/CLR]
ms.assetid: 5a73b275-aef0-4bda-8ae3-7c1196fe49c4
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 038fe6530c608d514b8fc326bfd2ac1026e1061d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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