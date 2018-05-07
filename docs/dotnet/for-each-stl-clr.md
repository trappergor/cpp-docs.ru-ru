---
title: for_each (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::for_each
dev_langs:
- C++
helpviewer_keywords:
- for_each function [STL/CLR]
ms.assetid: 4c391ecf-cd35-499e-a3f5-35b965e0da9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 54ce400f02e0b9fa04ab0e051234fa3eaef3182a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="foreach-stlclr"></a>for_each (STL/CLR)
Применяет заданный объект функции к каждому элементу в прямом порядке в пределах диапазона и возвращает объект функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _InIt, class _Fn1> inline  
    _Fn1 for_each(_InIt _First, _InIt _Last, _Fn1 _Func);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `for_each`. Дополнительные сведения см. в разделе [for_each](../standard-library/algorithm-functions.md#for_each).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)