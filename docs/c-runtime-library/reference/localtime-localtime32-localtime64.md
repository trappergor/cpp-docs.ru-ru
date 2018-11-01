---
title: localtime, _localtime32, _localtime64
ms.date: 11/04/2016
apiname:
- _localtime64
- _localtime32
- localtime
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
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
ms.openlocfilehash: d34a45ff20cb74d61a8eb189282bfdce4d8954ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629974"
---
# <a name="localtime-localtime32-localtime64"></a>localtime, _localtime32, _localtime64

Преобразует значение времени и корректирует его для местного часового пояса. Доступны более безопасные версии этих функций; см. раздел [localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md).

## <a name="syntax"></a>Синтаксис

```C
struct tm *localtime( const time_t *sourceTime );
struct tm *_localtime32( const __time32_t *sourceTime );
struct tm *_localtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Параметры

*sourceTime*<br/>
Указатель на сохраненное время.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на результирующую структуру или **NULL** Если дата, передаваемое функции:

- До полуночи 1-го января 1970 года.

- После 03:14:07 19 января 2038 года в формате UTC (с помощью **_time32** и **time32_t**).

- После 23:59:59 31 декабря 3000 года в формате UTC (с помощью **_time64** и **__time64_t**).

**_localtime64**, которая использует **__time64_t** структуры, допускает даты вверх до 23:59:59 31 декабря 3000 года скоординированного времени (UTC), тогда как функция **_localtime32** представляет даты до 23:59:59 18 января 2038 года в формате UTC.

**localtime** — это встроенная функция, результатом которого является **_localtime64**, и **time_t** эквивалентен **__time64_t**. Если вам нужно заставить компилятор интерпретировать **time_t** как старое 32-разрядное **time_t**, можно определить **_USE_32BIT_TIME_T**. Это приведет **localtime** для вычисления **_localtime32**. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.

Поля структуры типа [tm](../../c-runtime-library/standard-types.md) хранят следующие значения, каждое из которых является **int**:

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

Если **TZ** задана переменная среды, библиотеки времени выполнения C принимает правила, подходящие для США для реализации вычисления летнего времени (DST).

## <a name="remarks"></a>Примечания

**Localtime** функция преобразует время, хранящееся в виде [time_t](../../c-runtime-library/standard-types.md) значение и сохраняет результат в структуре типа [tm](../../c-runtime-library/standard-types.md). **Long** значение *sourceTime* представляет секунд, истекших после полуночи (00: 00:00), 1 января 1970 года в формате UTC. Это значение обычно получается из [время](time-time32-time64.md) функции.

32-разрядных и 64-разрядных версий из [gmtime](gmtime-gmtime32-gmtime64.md), [mktime](mktime-mktime32-mktime64.md), [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md), и **localtime** все используют один **tm** структуры на поток для преобразования. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова.

**localtime** исправляет для местного часового пояса, если пользователь сначала задает глобальную переменную среды **TZ**. Когда **TZ** задано три других переменных среды (**_timezone**, **_daylight**, и **_tzname**) также автоматически устанавливаются. Если **TZ** переменная не задана, **localtime** пытается использовать данные часового пояса, определенные в приложении Дата/время в панели управления. Если эти сведения недоступны, по умолчанию используется значение PST8PDT, что означает тихоокеанский часовой пояс. Описание этих переменных см. в разделе [_tzset](tzset.md). **TZ** — это расширение Microsoft и не является частью стандарта ANSI для **localtime**.

> [!NOTE]
> Целевая среда должна попытаться определить, действует ли летнее время.

Эти функции проверяют свои параметры. Если *sourceTime* является пустым указателем, или если *sourceTime* значение отрицательно, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, функции возвращают **NULL** и задайте **errno** для **EINVAL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|---------------------|-|
|**localtime**, **_localtime32**, **_localtime64**|\<time.h>|\<CTime > или \<time.h >|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_localtime.cpp
// compile with: /W3
// This program uses _time64 to get the current time
// and then uses localtime64() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm *newtime;
    char am_pm[] = "AM";
    __time64_t long_time;

    _time64( &long_time );             // Get time as 64-bit integer.
                                       // Convert to local time.
    newtime = _localtime64( &long_time ); // C4996
    // Note: _localtime64 deprecated; consider _localetime64_s

    if( newtime->tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime->tm_hour > 12 )        // Convert from 24-hour
        newtime->tm_hour -= 12;        //   to 12-hour clock.
    if( newtime->tm_hour == 0 )        // Set hour to 12 if midnight.
        newtime->tm_hour = 12;

    char buff[30];
    asctime_s( buff, sizeof(buff), newtime );
    printf( "%.19s %s\n", buff, am_pm );
}
```

```Output
Tue Feb 12 10:05:58 AM
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
