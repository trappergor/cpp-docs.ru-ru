---
title: _RTC_SetErrorFuncW
ms.date: 11/04/2016
api_name:
- _RTC_SetErrorFuncW
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
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
ms.openlocfilehash: 0d45e5c857e917ca23b62482c64a06314565226e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948964"
---
# <a name="_rtc_seterrorfuncw"></a>_RTC_SetErrorFuncW

Назначает функцию в качестве обработчика для сообщений о проверке на ошибки во время выполнения (RTC).

## <a name="syntax"></a>Синтаксис

```C
_RTC_error_fnW _RTC_SetErrorFuncW(
   _RTC_error_fnW function
);
```

### <a name="parameters"></a>Параметры

*function*<br/>
Адрес функции, которая будет обрабатывать проверки на ошибки во время выполнения.

## <a name="return-value"></a>Возвращаемое значение

Ранее определенная функция ERROR; или **значение NULL** , если ранее определенная функция отсутствует.

## <a name="remarks"></a>Примечания

В новом коде используйте только **_RTC_SetErrorFuncW**. **_RTC_SetErrorFunc** включается в библиотеку только для обеспечения обратной совместимости.

Обратный вызов **_RTC_SetErrorFuncW** применяется только к компоненту, с которым он был связан, но не глобально.

Убедитесь, что адрес, который вы передали в **_RTC_SetErrorFuncW** , является допустимой функцией обработки ошибок.

Если ошибке был присвоен тип-1 с помощью [_RTC_SetErrorType](rtc-seterrortype.md), функция обработки ошибок не вызывается.

Перед тем, как вы сможете вызвать эту функцию, необходимо сначала вызвать одну из функций инициализации проверки на ошибки во время выполнения. Для получения дополнительной информации см. [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).

**_RTC_error_fnW** определяется следующим образом:

```cpp
typedef int (__cdecl * _RTC_error_fnW)(
    int errorType,
    const wchar_t * filename,
    int linenumber,
    const wchar_t * moduleName,
    const wchar_t * format,
    ... );
```

где:

*errorType*<br/>
Тип ошибки, указанной [_RTC_SetErrorType](rtc-seterrortype.md).

*filename*<br/>
Исходный файл, где произошел сбой, или значение NULL, если информация об отладке недоступна.

*linenumber*<br/>
Строка *filename* , где произошел сбой, или 0, если информация об отладке недоступна.

*имя модуля*<br/>
Библиотека DLL или имя исполняемого файла, где произошел сбой.

*format*<br/>
Строка в стиле printf для отображения сообщения об ошибке с использованием оставшихся параметров. Первый аргумент VA_ARGLIST — номер возникшей ошибки RTC.

Пример, в котором показано, как использовать **_RTC_error_fnW**, см. в разделе [Настройка проверок во время выполнения машинного кода](/visualstudio/debugger/native-run-time-checks-customization).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapi.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Проверка ошибок во время выполнения](../../c-runtime-library/run-time-error-checking.md)<br/>
