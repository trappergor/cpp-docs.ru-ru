---
title: Уникальный (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::unique
dev_langs:
- C++
helpviewer_keywords:
- unique function [STL/CLR]
ms.assetid: 833cc314-b452-4659-bbb4-575c2bb63855
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 95e4ae3fe883f122f3a806dbcba017a0161c84b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164168"
---
# <a name="unique-stlclr"></a>unique (STL/CLR)
Удаляет повторяющиеся элементы, расположенные в указанном диапазоне рядом друг с другом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _FwdIt> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `unique`. Дополнительные сведения см. в разделе [уникальный](../standard-library/algorithm-functions.md#unique).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)