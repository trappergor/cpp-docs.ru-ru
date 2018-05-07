---
title: nth_element (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::nth_element
dev_langs:
- C++
helpviewer_keywords:
- nth_element function [STL/CLR]
ms.assetid: 19fc1695-62a9-4f85-9920-d153c1c6481f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4517ca62c7f7e376a13f2b3e02488d6c0256031a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nthelement-stlclr"></a>nth_element (STL/CLR)
Разделяет диапазон элементов, правильно находя `n`-ый элемент последовательности в диапазоне, чтобы все элементы перед ним были меньше или равны ему, а также все элементы, следующие за ней в последовательности, больше или равны ему.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _RanIt> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void nth_element(_RanIt _First, _RanIt _Nth, _RanIt _Last,  
        _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `nth_element`. Дополнительные сведения см. в разделе [nth_element](../standard-library/algorithm-functions.md#nth_element).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)