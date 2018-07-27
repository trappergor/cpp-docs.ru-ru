---
title: localtime_s, _localtime32_s, _localtime64_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _localtime64_s
- _localtime32_s
- localtime_s
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
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
dev_langs:
- C++
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 513bfe5baa16c9cae5052da084c65f580aad7f2e
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255812"
---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s, _localtime32_s, _localtime64_s

Преобразует **time_t** значение для времени **tm** структуры и выполняет коррекцию для местного часового пояса. Это версии функций [localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t localtime_s(
   struct tm* const tmDest,
   time_t const* const sourceTime
);
errno_t _localtime32_s(
   struct tm* tmDest,
   __time32_t const* sourceTime
);
errno_t _localtime64_s(
   struct tm* tmDest,
   __time64_t const* sourceTime
);
```

### <a name="parameters"></a>Параметры

*tmDest*<br/>
Указатель на структуру времени, которую требуется заполнить.

*sourceTime*<br/>
Указатель на хранимое время.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Условия ошибок

|*tmDest*|*sourceTime*|Возвращаемое значение|Значение в *tmDest*|Вызывает обработчик недопустимого параметра|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**NULL**|any|**EINVAL**|Без изменений|Да|
|Не **NULL** (указывает на допустимый адрес в памяти)|**NULL**|**EINVAL**|Во всех полях заданы значения –1|Да|
|Не **NULL** (указывает на допустимый адрес в памяти)|меньше 0 или больше, чем **_MAX__TIME64_T**|**EINVAL**|Во всех полях заданы значения –1|Нет|

В случае первых двух условий ошибки вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают **EINVAL**.

## <a name="remarks"></a>Примечания

**_Localtime32_s** функция преобразует время, хранящееся в виде [time_t](../../c-runtime-library/standard-types.md) и сохраняет результат в структуре типа [tm](../../c-runtime-library/standard-types.md). **Длинные** значение *sourceTime* представляет секунд, истекших после полуночи (00: 00:00), 1 января 1970 г., формат UTC. Это значение обычно получается из [время](time-time32-time64.md) функции.

**_localtime32_s** выполняет коррекцию для местного часового пояса, если пользователь сначала задает глобальную переменную среды **TZ**. Когда **TZ** задано три других переменных среды (**_timezone**, **_daylight**, и **_tzname**) автоматически устанавливается также. Если **TZ** переменная не задана, **localtime32_s** пытается использовать данные часового пояса, определенные в приложении Дата/время в панели управления. Если эти сведения недоступны, по умолчанию используется значение PST8PDT, что означает тихоокеанский часовой пояс. Описание этих переменных см. в разделе [_tzset](tzset.md). **TZ** представляет собой расширение Microsoft и не является частью стандарта ANSI для **localtime**.

> [!NOTE]
> Целевая среда должна попытаться определить, действует ли летнее время.

**_localtime64_s**, которая использует **__time64_t** структуры, позволяет даты вверх до 23:59:59, 18 января 3001, формате общего скоординированного времени (UTC), тогда как **_localtime32_s** представляет даты до 23:59:59 18 января 2038 года, время UTC.

**localtime_s** — это встроенная функция, которая принимает значение **_localtime64_s**, и **time_t** эквивалентно **__time64_t**. Если вам нужно заставляют компилятор интерпретировать **time_t** как старое 32-разрядное **time_t**, можно определить **_USE_32BIT_TIME_T**. Результате **localtime_s** будет вычисляться как **_localtime32_s**. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.

Поля типа структуры [tm](../../c-runtime-library/standard-types.md) хранения следующих значений, каждое из которых является **int**.

|Поле|Описание|
|-|-|
|**tm_sec**|Секунды после минуты (0 - 59).|
|**tm_min**|Минуты после часа (0 - 59).|
|**tm_hour**|Часы после полуночи (0 - 23).|
|**tm_mday**|День месяца (1-31).|
|**tm_mon**|Месяц (0 – 11; Январь = 0).|
|**tm_year**|Год (текущий год минус 1900).|
|**tm_wday**|День недели (0 – 6; Воскресенье = 0).|
|**tm_yday**|День года (0 – 365; 1 января = 0).|
|**tm_isdst**|Положительное значение, если действует летнее время; 0, если летнее время не действует; отрицательное значение, если состояние летнего времени неизвестно.|

Если **TZ** задана переменная среды, библиотеки времени выполнения C принимает правила, подходящие для США для реализации вычисления перехода на летнее время (DST).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|---------------------|-|
|**localtime_s**, **_localtime32_s**, **_localtime64_s**|\<time.h>|\<CTime > или \<time.h >|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_localtime_s.c
// This program uses _time64 to get the current time
// and then uses _localtime64_s() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm newtime;
    char am_pm[] = "AM";
    __time64_t long_time;
    char timebuf[26];
    errno_t err;

    // Get time as 64-bit integer.
    _time64( &long_time );
    // Convert to local time.
    err = _localtime64_s( &newtime, &long_time );
    if (err)
    {
        printf("Invalid argument to _localtime64_s.");
        exit(1);
    }
    if( newtime.tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime.tm_hour > 12 )        // Convert from 24-hour
        newtime.tm_hour -= 12;        // to 12-hour clock.
    if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.
        newtime.tm_hour = 12;

    // Convert to an ASCII representation.
    err = asctime_s(timebuf, 26, &newtime);
    if (err)
    {
        printf("Invalid argument to asctime_s.");
        exit(1);
    }
    printf( "%.19s %s\n", timebuf, am_pm );
}
```

```Output
Fri Apr 25 01:19:27 PM
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
