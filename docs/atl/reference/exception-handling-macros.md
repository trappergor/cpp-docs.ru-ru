---
title: Исключение Обработка Макрос
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 2beffbbed0efee799005190bd7fd071a2087e4d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330085"
---
# <a name="exception-handling-macros"></a>Исключение Обработка Макрос

Эти макросы обеспечивают поддержку обработки исключений.

|||
|-|-|
|[_ATLCATCH](#_atlcatch)|Заявление (ы) для обработки ошибок, возникающих в связанных. `_ATLTRY`|
|[_ATLCATCHALL](#_atlcatchall)|Заявление (ы) для обработки ошибок, возникающих в связанных. `_ATLTRY`|
|[_ATLTRY](#_atltry)|Отметки защищенного раздела кода, где может произойти ошибка.|

## <a name="requirements"></a>Требования

**Заголовок:** atldef.h

## <a name="_atlcatch"></a><a name="_atlcatch"></a>_ATLCATCH

Заявление (ы) для обработки ошибок, возникающих в связанных. `_ATLTRY`

```
_ATLCATCH(e)
```

### <a name="parameters"></a>Параметры

*E*<br/>
Исключение, чтобы поймать.

### <a name="remarks"></a>Remarks

Используется в сочетании со свойством `_ATLTRY`. Разрешает улов к C q [(CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) для обработки данного типа исключений C.

## <a name="_atlcatchall"></a><a name="_atlcatchall"></a>_ATLCATCHALL

Заявление (ы) для обработки ошибок, возникающих в связанных. `_ATLTRY`

```
_ATLCATCHALL
```

### <a name="remarks"></a>Remarks

Используется в сочетании со свойством `_ATLTRY`. Разрешает улов СЗ [(...)](../../cpp/try-throw-and-catch-statements-cpp.md) для обработки всех типов исключений C.

## <a name="_atltry"></a><a name="_atltry"></a>_ATLTRY

Отметки защищенного раздела кода, где может произойти ошибка.

```
_ATLTRY
```

### <a name="remarks"></a>Remarks

Используется в сочетании с [_ATLCATCH](#_atlcatch) или [_ATLCATCHALL.](#_atlcatchall) Разрешается [символу](../../cpp/try-throw-and-catch-statements-cpp.md)СЗ.

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
