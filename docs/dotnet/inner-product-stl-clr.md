---
title: inner_product (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::inner_product
dev_langs:
- C++
helpviewer_keywords:
- inner_product function [STL/CLR]
ms.assetid: 97d7a507-7494-4216-aedf-0546ed0edb3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b97b1a4be96e697c8e69db9c9d084780dd25d55f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="innerproduct-stlclr"></a>inner_product (STL/CLR)
Вычисляет сумму поэлементного умножения двух диапазонов и добавляет ее к указанному начальному значению либо вычисляет результат обобщенной процедуры, где бинарные операции суммы и умножения заменены на другие указанные бинарные операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _InIt1, class _InIt2, class _Ty> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val);  
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,  
       class _Fn22> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как числовая функция стандартной библиотеки C++ `inner_product`. Дополнительные сведения см. в разделе [inner_product](../standard-library/numeric-functions.md#inner_product).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/numeric >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)