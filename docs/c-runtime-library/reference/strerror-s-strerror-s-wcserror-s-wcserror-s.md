---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s
ms.date: 11/04/2016
api_name:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
ms.openlocfilehash: 74caba0398fdb5cdd0f9c80270a42d2903200a5d
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625812"
---
# <a name="strerror_s-_strerror_s-_wcserror_s-__wcserror_s"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

Получите системное сообщение об ошибке (**strerror_s**, **_wcserror_s**) или распечатайте сообщение об ошибке, предоставляемое пользователем ( **_strerror_s**, **__wcserror_s**). Это версии функций [strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

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

*стреррмсг*<br/>
Пользовательское сообщение.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

### <a name="error-condtions"></a>Условия ошибки

|*buffer*|*numberOfElements*|*стреррмсг*|Содержимое *буфера*|
|--------------|------------------------|-----------------|--------------------------|
|**NULL**|Любое действие|Любое действие|Н/Д|
|Любое действие|0|Любое действие|не изменено|

## <a name="remarks"></a>Заметки

Функция **strerror_s** сопоставляет *errnum* со строкой сообщения об ошибке, возвращая строку в *буфере*. **_strerror_s** не принимает номер ошибки; для определения соответствующего сообщения используется текущее **значение параметра «** ошибка». Ни **strerror_s** , ни **_strerror_s** на самом деле не выводят сообщение: для этого необходимо вызвать выходную функцию, например [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

Если *стреррмсг* имеет **значение NULL**, **_strerror_s** возвращает строку в *буфере* , содержащую системное сообщение об ошибке для последнего вызова библиотеки, вызвавшего ошибку. Строка сообщения об ошибке оканчивается символом новой строки ('\n'). Если *стреррмсг* не равно **null**, то **_strerror_s** возвращает строку в *буфере* , содержащую (по порядку) строковое сообщение, двоеточие, пробел, системное сообщение об ошибке для последнего вызова библиотеки, создающего ошибку, и символ новой строки символов. Длина сообщения строки не должна превышать 94 символа.

Эти функции обрезают сообщение об ошибке, если его длина превышает *numberOfElements* -1. Результирующая строка в *буфере* всегда завершается нулем.

Фактический номер ошибки для **_strerror_s** хранится в [переменной.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) Доступ к системным сообщениям об ошибках осуществляется через переменную [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), которая представляет собой массив сообщений об ошибке, отсортированный по номеру ошибки. **_strerror_s** обращается к соответствующему сообщению об ошибке, **используя значение пересчета в качестве** индекса для переменной **_sys_errlist**. Значение переменной [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) определяется как максимальное число элементов в массиве **_sys_errlist** . Чтобы получить точные результаты, вызовите **_strerror_s** сразу после возврата библиотечной программы с ошибкой. В противном случае последующие вызовы **strerror_s** или **_strerror_s** могут перезаписать **значение** перезаписи.

**_wcserror_s** и **__wcserror_s** — это версии **strerror_s** и **_strerror_s**для расширенных символов соответственно.

Эти функции проверяют свои параметры. Если параметр buffer имеет **значение NULL** или значение параметра size равно 0, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, функции возвращают **еинвал** и **присвойте** параметру перестройку значение **еинвал**.

**_strerror_s**, **_wcserror_s**и **__WCSERROR_S** не являются частью определения ANSI, но вместо них являются расширениями Майкрософт. Не используйте их, когда требуется переносимость. для совместимости с ANSI используйте вместо него **strerror_s** .

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Версии отладочной библиотеки этих функций сначала заполняют буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<string.h>|
|**_wcserror_s**, **__wcserror_s**|\<string.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [perror](perror-wperror.md).

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
