---
title: "adjacent_find (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::adjacent_find
dev_langs: C++
helpviewer_keywords: adjacent_find function
ms.assetid: 48bf57ea-b128-4d16-97c5-01d8a378369f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1cf088deace9f900007bee500f216fa2fbc8e7b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="adjacentfind-stlclr"></a>adjacent_find (STL/CLR)
Поиск двух соседних элементов, которые либо равны, либо удовлетворяют указанному условию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _FwdIt> inline  
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `adjacent_find`. Дополнительные сведения см. в разделе [adjacent_find](../standard-library/algorithm-functions.md#adjacent_find).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)