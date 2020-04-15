---
title: localtime_s, _localtime32_s, _localtime64_s
ms.date: 4/2/2020
api_name:
- _localtime64_s
- _localtime32_s
- localtime_s
- _o__localtime32_s
- _o__localtime64_s
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
ms.openlocfilehash: 3c5d194da85eb5d008dfc9cf19f222ebb575747d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342125"
---
# <a name="localtime_s-_localtime32_s-_localtime64_s"></a>localtime_s, _localtime32_s, _localtime64_s

Преобразует **значение time_t** времени в структуру **тм** и корректирует для локального часового пояса. Это версии функций [localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

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

*источникВремя*<br/>
Указатель на хранимое время.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*tmDest*|*источникВремя*|Возвращаемое значение|Значение в *tmDest*|Вызывает обработчик недопустимого параметра|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**Null**|any|**EINVAL**|Без изменений|Да|
|Не **NULL** (указывает на действительную память)|**Null**|**EINVAL**|Во всех полях заданы значения –1|Да|
|Не **NULL** (указывает на действительную память)|менее 0 или **больше,** чем _MAX__TIME64_T|**EINVAL**|Во всех полях заданы значения –1|нет|

В случае первых двух условий ошибки вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции установить **errno** **eINVAL** и вернуть **EINVAL**.

## <a name="remarks"></a>Remarks

Функция **localtime_s** преобразует время, хранящееся в [time_t](../../c-runtime-library/standard-types.md) значение, и сохраняет результат в структуре типа [tm.](../../c-runtime-library/standard-types.md) **Источник time_t** *значенияВремя* представляет секунды, прошедшие с полуночи (00:00:00), 1 января 1970 года, UTC. Это значение обычно получено из функции [времени.](time-time32-time64.md)

**localtime_s** корректирует для локального часового пояса, если пользователь впервые устанавливает глобальную переменную среды **ТЗ.** При установке **ТЗ** автоматически устанавливаются три другие переменные среды **(_timezone,** **_daylight**и **_tzname).** Если переменная **ТЗ** не установлена, **localtime_s** попытки использовать информацию часового пояса, указанную в приложении Дата/Время в панели управления. Если эти сведения недоступны, по умолчанию используется значение PST8PDT, что означает тихоокеанский часовой пояс. Описание этих переменных см. в разделе [_tzset](tzset.md). **ТЗ** является расширением Майкрософт и не является частью стандартного определения **местного времени**ANSI.

> [!NOTE]
> Целевая среда должна попытаться определить, действует ли летнее время.

**_localtime64_s**, который использует **__time64_t** структуру, позволяет даты, которые будут выражены через 23:59:59, 18 января 3001, скоординированное универсальное время (UTC), в то время как **_localtime32_s** представляет даты через 23:59:59 18 января 2038, UTC.

**localtime_s** является вневого функция, которая оценивает **_localtime64_s,** и **time_t** эквивалентно **__time64_t.** Если вам нужно заставить компилятор интерпретировать **time_t** как старый 32-разрядный **time_t,** вы можете определить **_USE_32BIT_TIME_T.** Это приведет к **localtime_s** **оценить,** чтобы _localtime32_s . Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.

Поля типа структуры [tm](../../c-runtime-library/standard-types.md) хранят следующие значения, каждое из которых является **int.**

|Поле|Описание|
|-|-|
|**tm_sec**|Секунды за минутой (0 - 59).|
|**tm_min**|Минуты за часом (0 - 59).|
|**tm_hour**|Часы с полуночи (0 - 23).|
|**tm_mday**|День месяца (1 - 31).|
|**tm_mon**|Месяц (0 - 11; Январь No 0).|
|**Tm_year**|Год (текущий год минус 1900).|
|**tm_wday**|День недели (0 - 6; Воскресенье No 0).|
|**Tm_yday**|День года (0 - 365; 1 января - 0).|
|**tm_isdst**|Положительное значение, если действует летнее время; 0, если летнее время не действует; отрицательное значение, если состояние летнего времени неизвестно.|

Если установлена переменная среды **ТЗ,** библиотека c run-time принимает правила, соответствующие Соединенным Штатам для реализации расчета летнего времени (DST).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|---------------------|-|
|**localtime_s,** **_localtime32_s,** **_localtime64_s**|\<time.h>|\<ctime> \<или time.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
