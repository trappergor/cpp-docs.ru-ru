---
title: Fill (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::fill
dev_langs:
- C++
helpviewer_keywords:
- fill function
ms.assetid: eb67241c-9bb3-497e-bec6-639900c60758
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2e1feaba4690bf64d28a7359b3be17d7e70a96f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fill-stlclr"></a>fill (STL/CLR)
Присваивает одно и то же новое значение каждому элементу в заданном диапазоне.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _FwdIt, class _Ty> inline  
    void fill(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `fill`. Дополнительные сведения см. в разделе [заполнения](../standard-library/algorithm-functions.md#fill).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)