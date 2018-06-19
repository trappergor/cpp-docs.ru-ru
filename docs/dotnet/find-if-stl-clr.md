---
title: find_if (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::find_if
dev_langs:
- C++
helpviewer_keywords:
- find_if function [STL/CLR]
ms.assetid: fd0db2be-a1e1-417e-8eea-653b08c9577e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b93718e2125d54852802170fd55cb2b5dd2840a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106275"
---
# <a name="findif-stlclr"></a>find_if (STL/CLR)
Находит позицию первого вхождения элемента, удовлетворяющего определенному условию, в диапазон.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _InIt, class _Pr> inline  
    _InIt find_if(_InIt _First, _InIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `find_if`. Дополнительные сведения см. в разделе [find_if](../standard-library/algorithm-functions.md#find_if).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)