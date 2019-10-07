---
title: _mkgmtime, _mkgmtime32, _mkgmtime64
ms.date: 11/04/2016
api_name:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
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
ms.openlocfilehash: fcd1e3fdcca37d7e5bb381c234a6d8555ce2766c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951671"
---
# <a name="_mkgmtime-_mkgmtime32-_mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64

Преобразует время в формате UTC, представленное **структурой** **TM** , в время в формате UTC, представленное типом **time_t** .

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

*timeptr*<br/>
Указатель на время в формате UTC в виде **структуры** **TM** для преобразования.

## <a name="return-value"></a>Возвращаемое значение

Количество типа **__time32_t** или **__time64_t** , представляющее количество секунд, истекших с полуночи 1 января 1970 г. в формате UTC. Если дата выходит за пределы допустимого диапазона (см. раздел "Примечания") или входные данные не могут интерпретироваться как допустимое время, возвращаемое значение равно-1.

## <a name="remarks"></a>Примечания

Функции **_mkgmtime32** и **_mkgmtime64** преобразуют время в формате UTC в тип **__time32_t** или **__time64_t** , представляющий время в формате UTC. Чтобы преобразовать местное время в время в формате UTC, используйте вместо него **функциях mktime**, **_mktime32**и **_mktime64** .

**_mkgmtime** — это встроенная функция, результатом которой является **_mkgmtime64**, а **time_t** эквивалентна **__time64_t**. Если необходимо заставить компилятор интерпретировать **time_t** как старый 32-разрядный **time_t**, можно определить **_USE_32BIT_TIME_T**. Это не рекомендуется, поскольку приложение может завершиться сбоем после 18 января 2038 (максимальный диапазон 32-бит **time_t**), и на 64-разрядных платформах это не разрешено.

Переданная структура времени будет изменена следующим образом, так же, как если бы они были изменены с помощью функций **_mktime** : поля **tm_wday** и **tm_yday** установлены на новые значения на основе значений **tm_mday** и **tm_year**. При указании времени структуры **TM** задайте для поля **tm_isdst** значение:

- нуль (0), чтобы указать, что действует стандартное время;

- значение больше нуля, чтобы указать, что действует переход на зимнее время;

- значение меньше нуля, чтобы указать, что код библиотеки времени выполнения языка C должен вычислить, действует ли стандартное время или переход на зимнее время.

Библиотека времени выполнения языка C использует переменную среды TZ для определения правильного летнего времени. Если TZ не задана, для получения верного регионального поведения по летнему времени отправляется запрос операционной системе. **tm_isdst** является обязательным полем. Если не задано, его значение не определено и возвращаемое значение из **функциях mktime** является непредсказуемым.

Диапазон функции **_mkgmtime32** — от полуночи 1 января 1970 г., utc – 23:59:59 18, 2038, UTC. Диапазон **_mkgmtime64** — от полуночи 1 января 1970 г., время в формате utc до 23:59:59, 31 декабря 3000, UTC. Дата вне диапазона приводит к возвращению значения-1. Диапазон **_mkgmtime** зависит от того, определен ли **_USE_32BIT_TIME_T** . Если значение не определено (по умолчанию), то диапазон равен **_mkgmtime64**; в противном случае диапазон ограничен 32-битным диапазоном **_mkgmtime32**.

Обратите внимание, что **gmtime** и **localtime** используют один статически выделенный буфер для преобразования. При указании этого буфера для **мкгмтиме**предыдущее содержимое уничтожается.

## <a name="example"></a>Пример

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

### <a name="sample-output"></a>Пример результатов выполнения

```Output
Seconds since midnight, January 1, 1970
My time: 1171588492
GM time (UTC): 1171588492

Local Time: Thu Feb 15 17:14:52 2007

Greenwich Mean Time: Fri Feb 16 01:14:52 2007
```

В следующем примере показано, как неполная структура заполняется вычисленными значения дня недели и дня года.

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

### <a name="output"></a>Вывод

```Output
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003
t.tm_yday = 0
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003
t.tm_yday = 42
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
