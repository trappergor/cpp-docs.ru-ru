---
title: "make_heap (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::make_heap
dev_langs: C++
helpviewer_keywords: make_heap function [STL/CLR]
ms.assetid: bc1bed28-7a26-4540-901d-5584cd117ea1
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 970cbe054aed2f5809e5acc05bad480e8f634349
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="makeheap-stlclr"></a>make_heap (STL/CLR)
Преобразует элементы из указанного диапазона в кучу, в которой первый элемент является наибольшим и для которой критерий сортировки может быть определен бинарным предикатом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _RanIt> inline  
    void make_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void make_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `make_heap`. Дополнительные сведения см. в разделе [make_heap](../standard-library/algorithm-functions.md#make_heap).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)