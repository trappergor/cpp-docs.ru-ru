---
title: "remove_copy (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::remove_copy
dev_langs: C++
helpviewer_keywords: remove_copy function [STL/CLR]
ms.assetid: 602fd8e3-26f7-491f-bf2c-cddf269f9807
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9d4b7a400e089ec8fb4be21e39f31b5562c5df24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="removecopy-stlclr"></a>remove_copy (STL/CLR)
Копирует элементы из исходного диапазона в диапазон назначения за исключением того, что элементы с заданным значением не копируются, не нарушая порядок остальных элементов и возвращая конец нового диапазона назначения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt remove_copy(_InIt _First, _InIt _Last,  
        _OutIt _Dest, const _Ty% _Val);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `remove_copy`. Дополнительные сведения см. в разделе [remove_copy](../standard-library/algorithm-functions.md#remove_copy).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)