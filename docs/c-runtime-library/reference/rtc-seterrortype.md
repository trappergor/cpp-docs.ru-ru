---
title: _RTC_SetErrorType
ms.date: 11/04/2016
api_name:
- _RTC_SetErrorType
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- RTC_SetErrorType
- _RTC_SetErrorType
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
ms.openlocfilehash: 6c1eff5920931aa3b72bf3dbc6232c371828b16a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948927"
---
# <a name="_rtc_seterrortype"></a>_RTC_SetErrorType

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
Значение, присваиваемое *errnum*. Например, можно использовать **_CRT_ERROR**. Если в качестве обработчика ошибок используется **_CrtDbgReport** , *ErrType* может быть только одним из символов, определенных в [_CrtSetReportMode](crtsetreportmode.md). Если у вас есть собственный обработчик ошибок ([_RTC_SetErrorFunc](rtc-seterrorfunc.md)), у вас может быть столько же *ErrType*, сколько *errnum*.

*ERRTYPE* _RTC_ERRTYPE_IGNORE имеет специальное значение для **_CrtSetReportMode**; ошибка игнорируется.

## <a name="return-value"></a>Возвращаемое значение

Предыдущее *значение типа ошибки.*

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
