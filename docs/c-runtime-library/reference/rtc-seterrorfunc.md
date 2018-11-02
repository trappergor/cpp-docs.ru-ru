---
title: _RTC_SetErrorFunc
ms.date: 11/04/2016
apiname:
- _RTC_SetErrorFunc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- RTC_SetErrorFunc
- _RTC_SetErrorFunc
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
ms.openlocfilehash: 6b292d685eea8eccb9e9b2a3c3e6cd903d501005
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514742"
---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc

Назначает функцию в качестве обработчика для сообщений о проверке на ошибки во время выполнения (RTC). Эта функция устарела; Используйте **_RTC_SetErrorFuncW** вместо этого.

## <a name="syntax"></a>Синтаксис

```C
_RTC_error_fn _RTC_SetErrorFunc(
   _RTC_error_fn function
);
```

### <a name="parameters"></a>Параметры

*function*<br/>
Адрес функции, которая будет обрабатывать проверки на ошибки во время выполнения.

## <a name="return-value"></a>Возвращаемое значение

Ранее определенная функция обработки ошибок. Если нет ранее определенной функции, возвращает **NULL**.

## <a name="remarks"></a>Примечания

Не используйте эту функцию; Вместо этого используйте **_RTC_SetErrorFuncW**. Она сохраняется только для обратной совместимости.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_RTC_SetErrorFunc**|\<rtcapi.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Проверка ошибок во время выполнения](../../c-runtime-library/run-time-error-checking.md)<br/>
