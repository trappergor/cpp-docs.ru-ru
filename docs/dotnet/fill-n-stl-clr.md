---
title: fill_n (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::fill_n
dev_langs:
- C++
helpviewer_keywords:
- fill_n function
ms.assetid: bb9f2f71-ba1d-44ec-8b47-6ece149dd6b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 242061a23f7d3979daf717d0b6c34ee5176e0cce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="filln-stlclr"></a>fill_n (STL/CLR)
Назначает новое значение указанному количеству элементов в диапазоне, начиная с определенного элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _OutIt, class _Diff, class _Ty> inline  
    void fill_n(_OutIt _First, _Diff _Count, const _Ty% _Val);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `fill_n`. Дополнительные сведения см. в разделе [fill_n](../standard-library/algorithm-functions.md#fill_n).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)