---
title: strerror, _strerror, _wcserror, __wcserror
ms.date: 11/04/2016
apiname:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 4038fcc29c18e5d73024cbe5688c674e00d1409e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594653"
---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror, _strerror, _wcserror, __wcserror

Получает системную строку сообщения об (**strerror**, **_wcserror**) или форматирует строку сообщения пользовательские ошибки (**_strerror**, **__wcserror**). Существуют более безопасные версии этих функций; см. раздел [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *strerror(
   int errnum
);
char *_strerror(
   const char *strErrMsg
);
wchar_t * _wcserror(
   int errnum
);
wchar_t * __wcserror(
   const wchar_t *strErrMsg
);
```

### <a name="parameters"></a>Параметры

*errnum*<br/>
Номер ошибки.

*strErrMsg*<br/>
Пользовательское сообщение.

## <a name="return-value"></a>Возвращаемое значение

Все эти функции возвращают указатель на строку сообщения об ошибке. Последующие вызовы могут перезаписать строку.

## <a name="remarks"></a>Примечания

**Strerror** функции карты *errnum* строку сообщения об ошибке и возвращает указатель на строку. Ни **strerror** , ни **_strerror** фактическую печать сообщения: для этого необходимо вызвать функцию вывода, такие как [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

Если *strErrMsg* передается в качестве **NULL**, **_strerror** возвращает указатель на строку, содержащую системное сообщение об ошибке для последнего вызова библиотеки, вызвавшего ошибку. Строка сообщения об ошибке оканчивается символом новой строки ('\n'). Если *strErrMsg* не равно **NULL**, затем **_strerror** возвращает указатель на строку, содержащую (в порядке) строку сообщения, двоеточие, пробел, системная ошибка сообщение для последнего вызова библиотеки, которая создает ошибку и символа новой строки. Длина сообщения строки не должна превышать 94 символа.

Фактический номер ошибки для **_strerror** хранится в переменной [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Чтобы обеспечить точные результаты, вызовите **_strerror** сразу же после подпрограмма библиотеки возвращает ошибку. В противном случае последующие вызовы **strerror** или **_strerror** можно перезаписать **errno** значение.

**_wcserror** и **__wcserror** представляют собой двухбайтовые версии **strerror** и **_strerror**, соответственно.

**_strerror**, **_wcserror**, и **__wcserror** не являются частью определения ANSI; они являются расширениями Майкрософт, и мы рекомендуем не использовать их место переносимого кода. Для обеспечения совместимости с ANSI используйте **strerror** вместо этого.

Для получения строк ошибок рекомендуется **strerror** или **_wcserror** вместо нерекомендуемых макросов [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) и [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) и внутренних функций **__sys_errlist** и **__sys_nerr**.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**, **__wcserror**|\<string.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [perror](perror-wperror.md).

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
