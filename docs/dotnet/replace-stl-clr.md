---
title: "Замените (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::replace
dev_langs: C++
helpviewer_keywords: replace function [STL/CLR]
ms.assetid: 3792abca-8d73-476a-8540-c5f739aa48c2
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fe1f9cf94f39deb2a8db662a149a625b035b8567
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="replace-stlclr"></a>replace (STL/CLR)
Проверяет каждый элемент в диапазоне и заменяет его, если он соответствует заданному значению.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _FwdIt, class _Ty> inline  
    void replace(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Oldval, const _Ty% _Newval);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `replace`. Дополнительные сведения см. в разделе [заменить](../standard-library/algorithm-functions.md#replace).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)