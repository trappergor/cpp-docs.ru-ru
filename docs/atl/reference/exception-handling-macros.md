---
title: Макросы для обработки исключений
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 8afb2019e38f7548467e85d9a2c1c12c538cf744
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276265"
---
# <a name="exception-handling-macros"></a>Макросы для обработки исключений

Эти макросы обеспечивают поддержку обработки исключений.

|||
|-|-|
|[_ATLCATCH](#_atlcatch)|Операторы обработки ошибок, возникших в соответствующем `_ATLTRY`.|
|[_ATLCATCHALL](#_atlcatchall)|Операторы обработки ошибок, возникших в соответствующем `_ATLTRY`.|
|[_ATLTRY](#_atltry)|Помечает раздел защищенный код, где возможно может возникнуть ошибка.|

## <a name="requirements"></a>Требования:

**Заголовок:** atldef.h

##  <a name="_atlcatch"></a>  _ATLCATCH

Операторы обработки ошибок, возникших в соответствующем `_ATLTRY`.

```
_ATLCATCH(e)
```

### <a name="parameters"></a>Параметры

*e*<br/>
Чтобы перехватить исключение.

### <a name="remarks"></a>Примечания

Используется в сочетании с `_ATLTRY`. Разрешается в C++ [catch (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) для обработки данного типа исключения C++.

##  <a name="_atlcatchall"></a>  _ATLCATCHALL

Операторы обработки ошибок, возникших в соответствующем `_ATLTRY`.

```
_ATLCATCHALL
```

### <a name="remarks"></a>Примечания

Используется в сочетании с `_ATLTRY`. Разрешается в C++ [catch(...) ](../../cpp/try-throw-and-catch-statements-cpp.md) для обработки всех типов исключений C++.

##  <a name="_atltry"></a>  _ATLTRY

Помечает раздел защищенный код, где возможно может возникнуть ошибка.

```
_ATLTRY
```

### <a name="remarks"></a>Примечания

Используется в сочетании с [_ATLCATCH](#_atlcatch) или [_ATLCATCHALL](#_atlcatchall). Разрешается в символ C++ [попробуйте](../../cpp/try-throw-and-catch-statements-cpp.md).

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
