---
title: _strtime_s, _wstrtime_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wstrtime_s
- _strtime_s
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wstrtime_s
- strtime_s
- wstrtime_s
- _strtime_s
dev_langs:
- C++
helpviewer_keywords:
- wstrtime_s function
- copying time to buffers
- strtime_s function
- _wstrtime_s function
- time, copying
- _strtime_s function
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2322f9be760faf36c2443d190229a4c67b47582b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="strtimes-wstrtimes"></a>_strtime_s, _wstrtime_s

Копирует текущее время в буфер. Это версии функции [_strtime, _wstrtime](strtime-wstrtime.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _strtime_s(
   char *buffer,
   size_t numberOfElements
);
errno_t _wstrtime_s(
   wchar_t *buffer,
   size_t numberOfElements
);
template <size_t size>
errno_t _strtime_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrtime_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Буфер длиной не менее 10 символов, в который будет записано время.

*numberOfElements*<br/>
Размер буфера.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении.

Если возникает ошибка, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определены в ERRNO.H; ошибки, создаваемые этой функцией, см. в таблице ниже. Дополнительные сведения о кодах ошибок см. в разделе [Константы errno](../../c-runtime-library/errno-constants.md).

### <a name="error-conditions"></a>Условия ошибок

|*buffer*|*numberOfElements*|Назад|Содержимое *буфера*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(любые)|**EINVAL**|Без изменений|
|Не **NULL** (с указанием допустимый буфер)|0|**EINVAL**|Без изменений|
|Не **NULL** (с указанием допустимый буфер)|0 < size < 9|**EINVAL**|Пустая строка|
|Не **NULL** (с указанием допустимый буфер)|Size > 9|0|Текущая дата в формате, указанном в разделе "Примечания"|

## <a name="security-issues"></a>Проблемы безопасности

Передача в недопустимое значение отличное от NULL для буфера приводит к нарушению прав доступа, если *numberOfElements* параметра больше 9.

При передаче значения *numberOfElements* , больше, чем фактический размер буфера приведет к переполнению буфера.

## <a name="remarks"></a>Примечания

Эти функции предоставляют более безопасные версии [_strtime](strtime-wstrtime.md) и [_wstrtime](strtime-wstrtime.md). **_Strtime_s** функция копирует текущее местное время в буфере, на который указывает *timestr*. Время форматируется как **чч** где **hh** состоит из двух цифр, представляющих час в 24-часовом формате, **мм** состоит из двух цифр, представляющих минут с начала часа и **ss** состоит из двух цифр, представляющих секунды. Например, строка **18:23:44** представляет 23 минуты 44 секунд за 6 часов Размер буфера должен составлять не менее 9 байт; фактический размер указывается в качестве второго параметра.

**_wstrtime** — это двухбайтовая версия **_strtime**; аргумент и возвращаемое значение **_wstrtime** представляют собой строки расширенных символов. В остальном эти функции ведут себя одинаково.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых функций:

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime_s**|**_strtime_s**|**_strtime_s**|**_wstrtime_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_strtime_s**|\<time.h>|
|**_wstrtime_s**|\<time.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// strtime_s.c

#include <time.h>
#include <stdio.h>

int main()
{
    char tmpbuf[9];
    errno_t err;

    // Set time zone from TZ environment variable. If TZ is not set,
    // the operating system is queried to obtain the default value
    // for the variable.
    //
    _tzset();

    // Display operating system-style date and time.
    err = _strtime_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
      exit(1);
    }
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );
    err = _strdate_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
       exit(1);
    }
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );

}
```

```Output
OS time:            14:37:49
OS date:            04/25/03
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
