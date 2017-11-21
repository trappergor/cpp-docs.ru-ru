---
title: "Уникальный (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::unique
dev_langs: C++
helpviewer_keywords: unique function [STL/CLR]
ms.assetid: 833cc314-b452-4659-bbb4-575c2bb63855
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6336a5579be9172caf6addd89e8b3b1b022151db
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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