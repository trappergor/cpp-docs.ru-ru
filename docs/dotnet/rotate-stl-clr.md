---
title: "Поворот (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::rotate
dev_langs:
- C++
helpviewer_keywords:
- rotate function [STL/CLR]
ms.assetid: 61dc89a9-a928-4eb3-89d6-2f5927df0f13
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 82ede9e68bc15e9e534e1cec75930809197fc133
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rotate-stlclr"></a>rotate (STL/CLR)
Меняет местами элементы в двух соседних диапазонах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _FwdIt> inline  
    void rotate(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `rotate`. Дополнительные сведения см. в разделе [Поворот](../standard-library/algorithm-functions.md#rotate).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)