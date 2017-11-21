---
title: "Макросы обработки исключений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
dev_langs: C++
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 906f6d499da04a6bee9da18dbbb6ad4b463c8fa6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="exception-handling-macros"></a>Макросы обработки исключений
Эти макросы обеспечивают поддержку для обработки исключений.  
  
|||  
|-|-|  
|[_ATLCATCH](#_atlcatch)|Операторы обработки ошибок, возникающих в соответствующем блоке `_ATLTRY`.|  
|[_ATLCATCHALL](#_atlcatchall)|Операторы обработки ошибок, возникающих в соответствующем блоке `_ATLTRY`.|  
|[_ATLTRY](#_atltry)|Помечает раздел защищенный код, в которых возможно может возникнуть ошибка.|  
  
## <a name="requirements"></a>Требования:
**Заголовок:** atldef.h

##  <a name="_atlcatch"></a>_ATLCATCH  
 Операторы обработки ошибок, возникающих в соответствующем блоке `_ATLTRY`.  
  
```
_ATLCATCH(e)
```  
  
### <a name="parameters"></a>Параметры  
 *e*  
 Чтобы перехватить исключение.  
  
### <a name="remarks"></a>Примечания  
 Использовать в сочетании с `_ATLTRY`. Разрешается в C++ [catch (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) для обработки данного типа исключения C++.  
  
##  <a name="_atlcatchall"></a>_ATLCATCHALL  
 Операторы обработки ошибок, возникающих в соответствующем блоке `_ATLTRY`.  
  
```
_ATLCATCHALL
```  
  
### <a name="remarks"></a>Примечания  
 Использовать в сочетании с `_ATLTRY`. Разрешается в C++ [catch(...) ](../../cpp/try-throw-and-catch-statements-cpp.md) для обработки всех типов исключений C++.  
  
##  <a name="_atltry"></a>_ATLTRY  
 Помечает раздел защищенный код, в которых возможно может возникнуть ошибка.  
  
```
_ATLTRY
```  
  
### <a name="remarks"></a>Примечания  
 Использовать в сочетании с [_ATLCATCH](#_atlcatch) или [_ATLCATCHALL](#_atlcatchall). Разрешается в символ C++ [повторите](../../cpp/try-throw-and-catch-statements-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
