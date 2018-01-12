---
title: "find_if (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::find_if
dev_langs: C++
helpviewer_keywords: find_if function [STL/CLR]
ms.assetid: fd0db2be-a1e1-417e-8eea-653b08c9577e
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 99b2759e590ac596b6dcebd1ec54b585af9ee89a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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