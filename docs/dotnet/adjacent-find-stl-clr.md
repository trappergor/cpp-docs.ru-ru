---
title: adjacent_find (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::adjacent_find
dev_langs:
- C++
helpviewer_keywords:
- adjacent_find function
ms.assetid: 48bf57ea-b128-4d16-97c5-01d8a378369f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ce62fd96954adb122176e02eb19c00b63d4ebbb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102544"
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