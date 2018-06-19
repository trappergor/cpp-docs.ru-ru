---
title: iter_swap (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::iter_swap
dev_langs:
- C++
helpviewer_keywords:
- iter_swap function [STL/CLR]
ms.assetid: 9809c9f5-2ca6-4e9e-97c1-d7973d3134f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 99e24ccbecea583de2a86b3c88a0180b016eae92
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129643"
---
# <a name="iterswap-stlclr"></a>iter_swap (STL/CLR)
Меняет местами два значения, указанные парой определенных итераторов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    void iter_swap(_FwdIt1 _Left, _FwdIt2 _Right);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `iter_swap`. Дополнительные сведения см. в разделе [iter_swap](../standard-library/algorithm-functions.md#iter_swap).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)