---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s
ms.date: 11/04/2016
apiname:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
- wcserror_s
- __wcserror_s
- _tcserror_s
- _wcserror_s
- tcserror_s
- strerror_s
- _strerror_s
helpviewer_keywords:
- __wcserror_s function
- error messages, printing
- tcserror_s function
- printing error messages
- strerror_s function
- _wcserror_s function
- _tcserror_s function
- _strerror_s function
- wcserror_s function
- error messages, getting
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
ms.openlocfilehash: 00ff9d0df1a78d07eaa509201fb998b30396cc4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429644"
---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

Получить системное сообщение об ошибке (**strerror_s**, **_wcserror_s**) или распечатать сообщение об ошибке, предоставленное пользователем (**_strerror_s**, **__wcserror_s** ). Это версии функций [strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t strerror_s(
   char *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t _strerror_s(
   char *buffer,
   size_t numberOfElements,
   const char *strErrMsg
);
errno_t _wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t __wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *strErrMsg
);
template <size_t size>
errno_t strerror_s(
   char (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t _strerror_s(
   char (&buffer)[size],
   const char *strErrMsg
); // C++ only
template <size_t size>
errno_t _wcserror_s(
   wchar_t (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t __wcserror_s(
   wchar_t (&buffer)[size],
   const wchar_t *strErrMsg
); // C++ only
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Буфер для строки ошибки.

*numberOfElements*<br/>
Размер буфера.

*errnum*<br/>
Номер ошибки.

*strErrMsg*<br/>
Пользовательское сообщение.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

### <a name="error-condtions"></a>Условия ошибки

|*buffer*|*numberOfElements*|*strErrMsg*|Содержание *буфера*|
|--------------|------------------------|-----------------|--------------------------|
|**NULL**|any|any|Н/Д|
|any|0|any|не изменено|

## <a name="remarks"></a>Примечания

**Strerror_s** функции карты *errnum* строка сообщения об ошибке, возвращая строку в *буфера*. **_strerror_s** не принимает номер ошибки; она использует текущее значение **errno** для определения соответствующего сообщения. Ни **strerror_s** , ни **_strerror_s** фактическую печать сообщения: для этого необходимо вызвать функцию вывода, такие как [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

Если *strErrMsg* — **NULL**, **_strerror_s** возвращает строку в *буфера* содержащую системное сообщение об ошибке для последнего вызова библиотеки вызвавшего ошибку. Строка сообщения об ошибке оканчивается символом новой строки ('\n'). Если *strErrMsg* не равно **NULL**, затем **_strerror_s** возвращает строку в *буфера* содержащую (в порядке) строку сообщения, двоеточие, пробел, системное сообщение об ошибке для последнего вызова библиотеки, вызвавшего ошибку и символ новой строки. Длина сообщения строки не должна превышать 94 символа.

Эти функции усекают сообщение об ошибке, если его длина превышает *numberOfElements* -1. Результирующая строка в *буфера* завершается всегда нуль символом.

Фактический номер ошибки для **_strerror_s** хранится в переменной [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Доступ к системным сообщениям об ошибках осуществляется через переменную [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), которая представляет собой массив сообщений об ошибке, отсортированный по номеру ошибки. **_strerror_s** обращается к соответствующее сообщение об ошибке с помощью **errno** значение как индекс для переменной **_sys_errlist**. Значение переменной [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) определяется как максимальное число элементов в **_sys_errlist** массива. Чтобы обеспечить точные результаты, вызовите **_strerror_s** сразу же после подпрограмма библиотеки возвращает ошибку. В противном случае последующие вызовы **strerror_s** или **_strerror_s** можно перезаписать **errno** значение.

**_wcserror_s** и **__wcserror_s** представляют собой двухбайтовые версии **strerror_s** и **_strerror_s**, соответственно.

Эти функции проверяют свои параметры. Если буфер **NULL** или если параметр размера равен 0, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, функции возвращают **EINVAL** и задайте **errno** для **EINVAL**.

**_strerror_s**, **_wcserror_s**, и **__wcserror_s** не являются частью определения ANSI, а представляют собой расширения Microsoft к нему. Не используйте их которых требуется обеспечить переносимость; для обеспечения совместимости с ANSI используйте **strerror_s** вместо этого.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Отладочные версии этих функций сначала заполняют буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<string.h>|
|**_wcserror_s**, **__wcserror_s**|\<string.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [perror](perror-wperror.md).

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
