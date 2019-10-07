---
title: strerror, _strerror, _wcserror, __wcserror
ms.date: 11/04/2016
api_name:
- strerror
- _strerror
- _wcserror
- __wcserror
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
ms.openlocfilehash: 0b4d70687bc2f428162d035c80d6bc8525a8fb9e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958148"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror, _strerror, _wcserror, __wcserror

Возвращает строку сообщения о системной ошибке (**strerror**, **_wcserror**) или формат пользовательской строки сообщения об ошибке ( **_strerror**, **__wcserror**). Существуют более безопасные версии этих функций; см. раздел [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md).

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

*стреррмсг*<br/>
Пользовательское сообщение.

## <a name="return-value"></a>Возвращаемое значение

Все эти функции возвращают указатель на строку сообщения об ошибке. Последующие вызовы могут перезаписать строку.

## <a name="remarks"></a>Примечания

Функция **strerror** сопоставляет *errnum* со строкой сообщения об ошибке и возвращает указатель на строку. Ни **strerror** , ни **_strerror** на самом деле не выводят сообщение: Для этого необходимо вызвать выходную функцию, например [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

Если *стреррмсг* передается как **null**, **_strerror** возвращает указатель на строку, содержащую системное сообщение об ошибке для последнего вызова библиотеки, вызвавшего ошибку. Строка сообщения об ошибке оканчивается символом новой строки ('\n'). Если *стреррмсг* не равно **null**, то **_strerror** возвращает указатель на строку, содержащую (по порядку) строковое сообщение, двоеточие, пробел, системное сообщение об ошибке для последнего вызова библиотеки, который создает ошибку, и строку символов. Длина сообщения строки не должна превышать 94 символа.

Фактический номер ошибки для **_strerror** хранится в [переменной.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) Чтобы получить точные результаты, вызовите **_strerror** сразу после возврата библиотечной программы с ошибкой. В противном случае последующие вызовы **strerror** или **_strerror** могут перезаписать **значение** перезаписи.

**_wcserror** и **__wcserror** — это версии **strerror** и **_strerror**для расширенных символов соответственно.

**_strerror**, **_wcserror**и **__WCSERROR** не являются частью определения ANSI; они являются расширениями Майкрософт и не рекомендуют использовать их там, где нужен переносимый код. Для совместимости с ANSI используйте вместо него **strerror** .

Для получения строк ошибок рекомендуется использовать **strerror** или **_wcserror** вместо устаревших макросов [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) и [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) и устаревших внутренних функций **__sys_errlist** и **__sys_nerr**.

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
