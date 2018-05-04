---
title: Макросы обработки исключений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
dev_langs:
- C++
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05ee381aa792c252fc9b80107d25e15e7d1ecfca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

##  <a name="_atlcatch"></a>  _ATLCATCH  
 Операторы обработки ошибок, возникающих в соответствующем блоке `_ATLTRY`.  
  
```
_ATLCATCH(e)
```  
  
### <a name="parameters"></a>Параметры  
 *e*  
 Чтобы перехватить исключение.  
  
### <a name="remarks"></a>Примечания  
 Использовать в сочетании с `_ATLTRY`. Разрешается в C++ [catch (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) для обработки данного типа исключения C++.  
  
##  <a name="_atlcatchall"></a>  _ATLCATCHALL  
 Операторы обработки ошибок, возникающих в соответствующем блоке `_ATLTRY`.  
  
```
_ATLCATCHALL
```  
  
### <a name="remarks"></a>Примечания  
 Использовать в сочетании с `_ATLTRY`. Разрешается в C++ [catch(...) ](../../cpp/try-throw-and-catch-statements-cpp.md) для обработки всех типов исключений C++.  
  
##  <a name="_atltry"></a>  _ATLTRY  
 Помечает раздел защищенный код, в которых возможно может возникнуть ошибка.  
  
```
_ATLTRY
```  
  
### <a name="remarks"></a>Примечания  
 Использовать в сочетании с [_ATLCATCH](#_atlcatch) или [_ATLCATCHALL](#_atlcatchall). Разрешается в символ C++ [повторите](../../cpp/try-throw-and-catch-statements-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
