---
title: prev_permutation (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::prev_permutation
dev_langs:
- C++
helpviewer_keywords:
- prev_permutation function [STL/CLR]
ms.assetid: 5294dbe5-1b5f-4369-a764-067dff86d1e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7ae545d56f6c9433e294a59f0af580e974e32ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33159383"
---
# <a name="prevpermutation-stlclr"></a>prev_permutation (STL/CLR)
Изменяет порядок элементов в диапазоне, чтобы исходный порядок был заменен перестановкой "лексикографически следующий больший", если такая существует, где смысл термина "следующий" может быть задан бинарным предикатом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _BidIt> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool prev_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `prev_permutation`. Дополнительные сведения см. в разделе [prev_permutation](../standard-library/algorithm-functions.md#prev_permutation).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)