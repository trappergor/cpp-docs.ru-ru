---
title: remove_if (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::remove_if
dev_langs:
- C++
helpviewer_keywords:
- remove_if function [STL/CLR]
ms.assetid: de501d3f-965b-4a99-b833-f6fa303fbcdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d481024679200c4c630dd6f739629937ea997db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33161243"
---
# <a name="removeif-stlclr"></a>remove_if (STL/CLR)
Удаляет элементы, соответствующие предикату, из заданного диапазона без нарушения порядка остальных элементов и возвращает конец нового диапазона после удаления указанного значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _FwdIt, class _Pr> inline  
    _FwdIt remove_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `remove_if`. Дополнительные сведения см. в разделе [remove_if](../standard-library/algorithm-functions.md#remove_if).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)