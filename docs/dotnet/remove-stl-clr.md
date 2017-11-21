---
title: "удалить (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::remove
dev_langs: C++
helpviewer_keywords: remove function [STL/CLR]
ms.assetid: 85a11883-3e25-49aa-b4a0-b2cffd6dc110
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 11badfc92a6b307c64f1fb9d4b24373173cae7a3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="remove-stlclr"></a>remove (STL/CLR)
Удаляет указанное значение из заданного диапазона без нарушения порядка остальных элементов и возвращает конец нового диапазона после удаления указанного значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _FwdIt, class _Ty> inline  
    _FwdIt remove(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `remove`. Дополнительные сведения см. в разделе [удалить](http://msdn.microsoft.com/Library/77e2585c-441e-448d-bd1d-c893d1356ed8).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)