---
title: _mkgmtime, _mkgmtime32, _mkgmtime64
description: Описывает _mkgmtime, _mkgmtime32 и _mkgmtime64 C Функции библиотеки И в Runtime и приводитпример, как их использовать.
ms.date: 4/2/2020
api_name:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
- _o__mkgmtime32
- _o__mkgmtime64
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
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
helpviewer_keywords:
- mkgmtime32 function
- time functions
- mkgmtime function
- _mkgmtime function
- converting times
- mkgmtime64 function
- _mkgmtime64 function
- _mkgmtime32 function
- time, converting
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
ms.openlocfilehash: e8b3170fc0413a878777035fd76aac5eefa7b6bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338774"
---
# <a name="_mkgmtime-_mkgmtime32-_mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64

Преобразует время UTC, представленное **структурируемым** **тм,** в время UTC, представленное **time_t** типом.

## <a name="syntax"></a>Синтаксис

```C
time_t _mkgmtime(
   struct tm* timeptr
);
__time32_t _mkgmtime32(
   struct tm* timeptr
);
__time64_t _mkgmtime64(
   struct tm* timeptr
);
```

### <a name="parameters"></a>Параметры

*таймтр*\
Указатель времени UTC как **структурировать** **tm** для преобразования.

## <a name="return-value"></a>Возвращаемое значение

Количество типа **__time32_t** или **__time64_t,** представляющих количество секунд, прошедших с полуночи, 1 января 1970 года, в скоординированном универсальном времени (UTC). Если дата находится вне диапазона (см. раздел Замечания) или вход не может быть истолкован как допустимое время, значение возврата -1.

## <a name="remarks"></a>Remarks

**Функции _mkgmtime32** и **_mkgmtime64** преобразуют время UTC в **__time32_t** или **__time64_t** тип, представляющий время в UTC. Чтобы преобразовать местное время во время UTC, используйте **mktime,** **_mktime32**и вместо этого **_mktime64.**

**_mkgmtime** является вневистой функцией, которая оценивает **_mkgmtime64,** и **time_t** эквивалентна **__time64_t.** Если вам нужно заставить компилятор интерпретировать **time_t** как старый 32-разрядный **time_t,** вы можете определить **_USE_32BIT_TIME_T.** Мы не рекомендуем его, потому что ваше приложение может вывести из строя после 18 января 2038, максимальный диапазон 32-битной **time_t**. Это не разрешено вообще на 64-битных платформах.

Структура времени, пройденные в меняется следующим образом, так же, как это изменено **_mktime** функций: **tm_wday** и **tm_yday** поля настроены на новые значения, основанные на значениях **tm_mday** и **tm_year**. Поскольку предполагается, что время ЯВЛЯЕТСЯ UTC, **tm_isdst** поле игнорируется.

Диапазон **_mkgmtime32** функции с полуночи, 1 января 1970 года, UTC до 23:59:59 18 января 2038, UTC. Диапазон **_mkgmtime64** с полуночи, 1 января 1970 года, UTC до 23:59:59, 31 декабря, 3000, UTC. Внедиапазона дата приводит к возврату значения -1. Диапазон **_mkgmtime** зависит от того, определяется ли **_USE_32BIT_TIME_T.** Когда он не определен, что по умолчанию, диапазон такой же, как **_mkgmtime64**. В противном случае диапазон ограничен 32-битным диапазоном **_mkgmtime32.**

Как **gmtime,** так и **местное время** используют общий статический буфер для преобразования. Если вы поставляете этот буфер **для _mkgmtime,** предыдущее содержимое будет уничтожено.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="examples"></a>Примеры

```C
// crt_mkgmtime.c
#include <stdio.h>
#include <time.h>

int main()
{
    struct tm t1, t2;
    time_t now, mytime, gmtime;
    char buff[30];

    time( & now );

    _localtime64_s( &t1, &now );
    _gmtime64_s( &t2, &now );

    mytime = mktime(&t1);
    gmtime = _mkgmtime(&t2);

    printf("Seconds since midnight, January 1, 1970\n");
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);

    /* Use asctime_s to display these times. */

    _localtime64_s( &t1, &mytime );
    asctime_s( buff, sizeof(buff), &t1 );
    printf( "Local Time: %s\n", buff );

    _gmtime64_s( &t2, &gmtime );
    asctime_s( buff, sizeof(buff), &t2 );
    printf( "Greenwich Mean Time: %s\n", buff );

}
```

```Output
Seconds since midnight, January 1, 1970
My time: 1171588492
GM time (UTC): 1171588492

Local Time: Thu Feb 15 17:14:52 2007

Greenwich Mean Time: Fri Feb 16 01:14:52 2007
```

Ниже приводится следующий пример, как неполная структура заполняется **_mkgmtime.** Он вычисляет значения как для дня недели, так и для года.

```C
// crt_mkgmtime2.c
#include <stdio.h>
#include <time.h>
#include <memory.h>

int main()
{
    struct tm t1, t2;
    time_t gmtime;
    char buff[30];

    memset(&t1, 0, sizeof(struct tm));
    memset(&t2, 0, sizeof(struct tm));

    t1.tm_mon = 1;
    t1.tm_isdst = 0;
    t1.tm_year = 103;
    t1.tm_mday = 12;

    // The day of the week and year will be incorrect in the output here.
    asctime_s( buff, sizeof(buff), &t1);
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

    gmtime = _mkgmtime(&t1);

    // The correct day of the week and year were determined.
    asctime_s( buff, sizeof(buff), &t1);
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

}
```

```Output
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003
t.tm_yday = 0
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003
t.tm_yday = 42
```

## <a name="see-also"></a>См. также раздел

[Управление временем](../../c-runtime-library/time-management.md)\
[asctime, _wasctime](asctime-wasctime.md)\
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)\
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)\
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[time, _time32, _time64](time-time32-time64.md)
