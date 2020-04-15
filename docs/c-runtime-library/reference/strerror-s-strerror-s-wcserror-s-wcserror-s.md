---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s
ms.date: 4/2/2020
api_name:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
- _o__strerror_s
- _o__wcserror_s
- _o_strerror_s
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
ms.openlocfilehash: ef712ecb6236513d169b4a8836b1365b0aca0633
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337368"
---
# <a name="strerror_s-_strerror_s-_wcserror_s-__wcserror_s"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

Получить сообщение об ошибке системы **(strerror_s,** **_wcserror_s)** или распечатать сообщение об ошибке, предоставленное пользователем **(_strerror_s,** **__wcserror_s).** Это версии функций [strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

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

*Буфера*<br/>
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

|*Буфера*|*numberOfElements*|*strErrMsg*|Содержимое *буфера*|
|--------------|------------------------|-----------------|--------------------------|
|**Null**|any|any|Недоступно|
|any|0|any|не изменено|

## <a name="remarks"></a>Remarks

**Функция strerror_s** карты *errnum* к строке сообщения об ошибке, возвращая строку в *буфере.* **_strerror_s** не берет номер ошибки; он использует текущее значение **errno** для определения соответствующего сообщения. Ни **strerror_s,** ни **_strerror_s** на самом деле не печатает сообщение: Для этого необходимо вызвать функцию вывода, такую как [fprintf:](fprintf-fprintf-l-fwprintf-fwprintf-l.md)

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

Если *strErrMsg* **null,** **_strerror_s** возвращает строку в *буфере,* содержащую сообщение об ошибке системы для последнего вызова библиотеки, который произвел ошибку. Строка сообщения об ошибке оканчивается символом новой строки ('\n'). Если *strErrMsg* не равен **NULL,** то **_strerror_s** возвращает строку в *буфере,* содержащую (в порядке) сообщение строки, толстую кишку, пространство, сообщение об ошибке системы для последнего вызова библиотеки, производящего ошибку, и новый символ строки. Длина сообщения строки не должна превышать 94 символа.

Эти функции усечение сообщения об ошибке, если его длина превышает *numberOfElements* -1. Полученная строка в *буфере* всегда сводится на нет.

Фактическое число ошибок для **_strerror_s** хранится в переменной [errno.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) Доступ к системным сообщениям об ошибках осуществляется через переменную [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), которая представляет собой массив сообщений об ошибке, отсортированный по номеру ошибки. **_strerror_s** получает доступ к соответствующему сообщению об ошибке, используя значение **errno** в качестве индекса к переменной **_sys_errlist.** Значение переменной [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) определяется как максимальное количество элементов в **массиве _sys_errlist.** Чтобы привести точные результаты, позвоните **_strerror_s** сразу после того, как рутина библиотеки возвращается с ошибкой. В противном случае последующие вызовы **strerror_s** или **_strerror_s** могут перезаписать значение **errno.**

**_wcserror_s** и **__wcserror_s** являются широкохарактерными версиями **strerror_s** и **_strerror_s**соответственно.

Эти функции проверяют свои параметры. Если буфер **NULL** или если параметр размера 0, вызовуется недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функции возвращают **EINVAL** и устанавливают **errno** **в EINVAL.**

**_strerror_s,** **_wcserror_s**и **__wcserror_s** не являются частью определения ANSI, но вместо этого Microsoft расширений к нему. Не используйте их там, где портативность является желаемой; для совместимости ANSI используйте вместо этого **strerror_s.**

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Отладка библиотеки версии этих функций сначала заполнить буфер с 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<string.h>|
|**_wcserror_s**, **__wcserror_s**|\<string.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [perror](perror-wperror.md).

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
