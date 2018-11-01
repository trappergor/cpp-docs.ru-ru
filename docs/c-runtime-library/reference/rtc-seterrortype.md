---
title: _RTC_SetErrorType
ms.date: 11/04/2016
apiname:
- _RTC_SetErrorType
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
- RTC_SetErrorType
- _RTC_SetErrorType
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
ms.openlocfilehash: 022079bd199477c8bca92e853ed66879c96428db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635682"
---
# <a name="rtcseterrortype"></a>_RTC_SetErrorType

Связывает обнаруженную проверкой во время выполнения ошибку (RTC) с типом. Обработчик ошибок определяет способ вывода ошибок указанного типа.

## <a name="syntax"></a>Синтаксис

```C
int _RTC_SetErrorType(
   _RTC_ErrorNumber errnum,
   int ErrType
);
```

### <a name="parameters"></a>Параметры

*errnum*<br/>
Число от нуля до единицы и меньше значения, возвращаемого [_RTC_NumErrors](rtc-numerrors.md).

*ErrType*<br/>
Значение, присваиваемое *errnum*. Например, можно использовать **_CRT_ERROR**. Если вы используете **_CrtDbgReport** как обработчика ошибок, *ErrType* может быть только один из символов, определенных в [_CrtSetReportMode](crtsetreportmode.md). Если у вас есть собственный обработчик ошибок ([_RTC_SetErrorFunc](rtc-seterrorfunc.md)), у вас может быть столько же *ErrType*, сколько *errnum*.

*ErrType* для _RTC_ERRTYPE_IGNORE имеет специальное значение для **_CrtSetReportMode**; Ошибка игнорируется.

## <a name="return-value"></a>Возвращаемое значение

Предыдущее значение для типа ошибки *тип*.

## <a name="remarks"></a>Примечания

По умолчанию для всех ошибок задается значение *ErrType* = 1, которое соответствует **_CRT_ERROR**. Дополнительные сведения о типах ошибок по умолчанию, таких как **_CRT_ERROR**, см. в статье об [_CrtDbgReport](crtdbgreport-crtdbgreportw.md).

Перед тем, как вы сможете вызвать эту функцию, необходимо сначала вызвать одну из функций инициализации проверок на ошибки во время выполнения; см. статью [Использование проверок во время выполнения без библиотеки времени выполнения C](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_RTC_SetErrorType**|\<rtcapi.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Проверка ошибок во время выполнения](../../c-runtime-library/run-time-error-checking.md)<br/>
