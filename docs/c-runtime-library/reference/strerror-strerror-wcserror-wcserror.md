---
title: strerror, _strerror, _wcserror, __wcserror
description: Описывает функции библиотеки Runtime (CRT) microsoft C( функции strerror, _strerror, _wcserror и __wcserror.
ms.date: 4/2/2020
api_name:
- strerror
- _strerror
- _wcserror
- __wcserror
- _o___wcserror
- _o__strerror
- _o__wcserror
- _o_strerror
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
ms.openlocfilehash: 9eecb7376cf476f0128dc20c8884746a3b4d47d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337332"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror, _strerror, _wcserror, __wcserror

Получает строку сообщения об ошибке системы **(strerror,** **_wcserror)** или форматирует строку сообщения об ошибке, поставляемую пользователем **(_strerror,** **__wcserror).** Существуют более безопасные версии этих функций; см. раздел [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md).

## <a name="syntax"></a>Синтаксис

```C
char * strerror(
   int errnum );

char * _strerror(
   const char *strErrMsg );

wchar_t * _wcserror(
   int errnum );

wchar_t * __wcserror(
   const wchar_t *strErrMsg );
```

### <a name="parameters"></a>Параметры

*errnum*\
Номер ошибки.

*strErrMsg*\
Пользовательское сообщение.

## <a name="return-value"></a>Возвращаемое значение

Все эти функции возвращают указатель строки сообщения об ошибке в буфере хранения, принадлежащем времени выполнения. Более поздние вызовы на тот же поток могут перезаписать эту строку.

## <a name="remarks"></a>Remarks

Функция **strerror** *отображает ошибку* в строке сообщения об ошибке и возвращает указатель в строку. **Функцияstrerror** и **_strerror** на самом деле не печатают сообщение. Для печати вызовите функцию вывода, такую как [fprintf:](fprintf-fprintf-l-fwprintf-fwprintf-l.md)

```C
if (( _access( "datafile", 2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

Если *strErrMsg* передается как **NULL,** **_strerror** возвращает указатель на строку. Он содержит сообщение об ошибке системы для последнего вызова библиотеки, который произвел ошибку. Строка сообщения об ошибке оканчивается символом новой строки ('\n'). Когда *strErrMsg* не **является NULL,** строка содержит, в порядке: ваш *strErrMsg* строки, толстой кишки, пространство, сообщение об ошибке системы, и новый символ строки. Ваше сообщение строки может быть, в лучшем случае, 94 символов длиной, либо в узких **(_strerror)** или широкий **(__wcserror)** символов.

Фактический номер ошибки для **_strerror** хранится в переменной [errno.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) Чтобы привести точные результаты, позвоните **_strerror** сразу же после того, как рутина библиотеки возвращает ошибку. В противном случае более поздние вызовы в библиотечные процедуры могут перезаписать значение **errno.**

**_wcserror** и **__wcserror** являются широкохарактерными версиями **strerror** и **_strerror**соответственно.

**_strerror,** **_wcserror**и **__wcserror** являются специфичными для Майкрософт, а не частью библиотеки Standard C. Мы не рекомендуем вам использовать их там, где вам нужен портативный код. Для совместимости Standard C используйте **strerror.**

Чтобы получить строки ошибки, мы рекомендуем **strerror** или **_wcserror** вместо deprecated [макросов _sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) и [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) и изунебренные внутренние функции **__sys_errlist** и **__sys_nerr.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Общие текстовые рутинные отображения

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**, **__wcserror**|\<string.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [perror](perror-wperror.md).

## <a name="see-also"></a>См. также раздел

[Манипуляция стрингами](../../c-runtime-library/string-manipulation-crt.md)\
[clearerr](clearerr.md)\
[Ферр](ferror.md)\
[perror, _wperror](perror-wperror.md)
