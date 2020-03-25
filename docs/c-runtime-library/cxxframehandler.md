---
title: __CxxFrameHandler
ms.date: 11/04/2016
api_name:
- __CxxFrameHandler
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __CxxFrameHandler
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
ms.openlocfilehash: db856850688e378cde9eaa1fb510cb325ce0644b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170986"
---
# <a name="__cxxframehandler"></a>__CxxFrameHandler

Внутренняя функция CRT. Используется CRT для обработки кадров структурированной обработки исключений.

## <a name="syntax"></a>Синтаксис

```cpp
EXCEPTION_DISPOSITION __CxxFrameHandler(
      EHExceptionRecord  *pExcept,
      EHRegistrationNode *pRN,
      void               *pContext,
      DispatcherContext  *pDC
   )
```

#### <a name="parameters"></a>Параметры

*pExcept*<br/>
Запись исключения, передаваемая в возможные операторы `catch`.

*pRN*<br/>
Динамические сведения о кадре стека, который используется для обработки исключения. Дополнительные сведения см. в описании ehdata.h.

*pContext*<br/>
Контекст. (Не используется для процессоров Intel.)

*pDC*<br/>
Дополнительные сведения о входе в функцию и кадре стека.

## <a name="return-value"></a>Возвращаемое значение

Одно из значений *выражения фильтра*, используемое в [операторе try-except](../cpp/try-except-statement.md).

## <a name="remarks"></a>Remarks

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|__CxxFrameHandler|excpt.h, ehdata.h|
