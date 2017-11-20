---
title: "replace_copy_if (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::replace_copy_if
dev_langs: C++
helpviewer_keywords: replace_copy_if function [STL/CLR]
ms.assetid: 60edf9b8-34e6-4d94-a611-363ef7b7fb80
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e144636c5d1ce1a4ae7776ccedf675d5db473d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="replacecopyif-stlclr"></a>replace_copy_if (STL/CLR)
Проверяет каждый элемент в исходном диапазоне и заменяет его, если он соответствует заданному предикату, одновременно копируя результат в новый диапазон назначения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _InIt, class _OutIt, class _Pr, class _Ty> inline  
    _OutIt replace_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred, const _Ty% _Val);  
```  
  
## <a name="remarks"></a>Примечания  
 Эта функция работает так же, как функция стандартной библиотеки C++ `replace_copy_if`. Дополнительные сведения см. в разделе [replace_copy_if](../standard-library/algorithm-functions.md#replace_copy_if).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/алгоритм >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)