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
ms.workload: cplusplus
ms.openlocfilehash: 424a65c44d7bb22d1fef6e21e1892967ecd3e9b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
