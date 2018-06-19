---
title: секции (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::partition
dev_langs:
- C++
helpviewer_keywords:
- partition function [STL/CLR]
ms.assetid: 3f551eb3-31ec-4b1d-b585-07718d6a1bd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 91da41eee64ca5f818cb8dfcbc9a7517f3aed144
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33159240"
---
# <a name="partition-stlclr"></a>partition (STL/CLR)
Разделяет элементы диапазона на два непересекающихся множества, при этом элементы, удовлетворяющие унарному предикату, расположены перед теми, которые ему не удовлетворяют.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _BidIt, class _Pr> inline  
    _BidIt partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `partition`. Дополнительные сведения см. в разделе [секции](../standard-library/algorithm-functions.md#partition).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)