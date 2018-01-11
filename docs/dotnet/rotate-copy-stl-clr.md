---
title: "rotate_copy (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::rotate_copy
dev_langs: C++
helpviewer_keywords: rotate_copy function [STL/CLR]
ms.assetid: ed697552-130f-474f-9ab6-133332bb2587
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 19914d41d64c184e66324006c06a0e37e91c6393
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rotatecopy-stlclr"></a>rotate_copy (STL/CLR)
Меняет местами элементы в двух соседних диапазонах в пределах исходного диапазона и копирует результат в диапазон назначения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _FwdIt, class _OutIt> inline  
    _OutIt rotate_copy(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last,  
        _OutIt _Dest);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `rotate_copy`. Дополнительные сведения см. в разделе [rotate_copy](../standard-library/algorithm-functions.md#rotate_copy).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)