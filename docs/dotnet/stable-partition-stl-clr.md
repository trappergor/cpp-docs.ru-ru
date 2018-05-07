---
title: stable_partition (STL/CLR) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stable_partition
dev_langs:
- C++
helpviewer_keywords:
- stable_partition function [STL/CLR]
ms.assetid: b82c194c-ae38-4afb-b255-a95a4c2b3101
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4629f4a0e6d30d454db08a56c6d8cb5f7be991cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="stablepartition-stlclr"></a>stable_partition (STL/CLR)
Разделяет элементы диапазона на два непересекающихся множества, при этом элементы, удовлетворяющие унарному предикату, расположены перед теми, которые ему не удовлетворяют, с сохранением относительного порядка равноценных элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _BidIt, class _Pr> inline  
    _BidIt stable_partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `stable_partition`. Дополнительные сведения см. в разделе [stable_partition](../standard-library/algorithm-functions.md#stable_partition).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)