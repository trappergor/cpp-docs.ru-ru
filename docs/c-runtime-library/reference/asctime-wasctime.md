---
title: asctime, _wasctime
ms.date: 11/04/2016
apiname:
- _wasctime
- asctime
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
- _tasctime
- asctime
- _wasctime
helpviewer_keywords:
- asctime function
- tasctime function
- wasctime function
- _tasctime function
- _wasctime function
- time structure conversion
- time, converting
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
ms.openlocfilehash: bc2d7a50442d9000eaaebf7a06bf336b3317e4df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341812"
---
# <a name="asctime-wasctime"></a>asctime, _wasctime

Преобразовать **tm** структуру в символьную строку времени. Существуют более безопасные версии этих функций; см. раздел [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *asctime(
   const struct tm *timeptr
);
wchar_t *_wasctime(
   const struct tm *timeptr
);
```

### <a name="parameters"></a>Параметры

*timeptr*<br/>
Структура даты/времени.

## <a name="return-value"></a>Возвращаемое значение

**asctime** возвращает указатель на результирующую строку символов; **_wasctime** возвращает указатель на результирующую строку расширенных символов. Код ошибки не возвращается.

## <a name="remarks"></a>Примечания

Существуют более безопасные версии этих функций; см. раздел [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

**Asctime** функция преобразует время, хранящееся в виде структуры в символьную строку. *Timeptr* значение обычно получается из вызова **gmtime** или **localtime**, которые возвращают указатель на **tm** структуры, определен во времени. З.

|Член timeptr|Значение|
|--------------------|-----------|
|**tm_hour**|Часы после полуночи (0-23)|
|**tm_isdst**|Положительно, если действует летнее время; 0 если летнее время не действует; отрицательно, если состояние летнего времени неизвестно. Библиотека времени выполнения C принимает правила Соединенных Штатов для реализации проверки на летнее время (DST).|
|**tm_mday**|День месяца (1-31)|
|**tm_min**|Минуты после часа (0-59)|
|**tm_mon**|Месяц (0 – 11; Январь = 0)|
|**tm_sec**|Секунды после минуты (0-59)|
|**tm_wday**|День недели (0 – 6; Воскресенье = 0)|
|**tm_yday**|День года (0 – 365; 1 января = 0)|
|**tm_year**|Год (текущий год минус 1900)|

Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. Дополнительные сведения о настройке местного времени см. в описании функций [time](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md) и [localtime](localtime-localtime32-localtime64.md). Сведения об определении среды часового пояса и глобальных переменных см. в описании функции [_tzset](tzset.md).

Строка, полученная путем **asctime** содержит ровно 26 символов и имеет вид `Wed Jan 02 02:03:55 1980\n\0`. Время в 24-часовом формате. Все поля имеют постоянную ширину. Символ новой строки и нуль-символ занимают две последние позиции строки. **asctime** использует один статически выделяемый буфер для хранения возвращаемой строки. Каждый вызов этой функции уничтожает результат предыдущего вызова.

**_wasctime** — это двухбайтовая версия **asctime**. **_wasctime** и **asctime** идентично в противном случае.

Эти функции проверяют свои параметры. Если *timeptr* является пустым указателем, или если он содержит значения вне диапазона, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает **NULL** и задает **errno** для **EINVAL**.

### <a name="generic-text-routine-mapping"></a>Сопоставление универсальных текстовых функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime**|**asctime**|**asctime**|**_wasctime**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**asctime**|\<time.h>|
|**_wasctime**|\<time.h> или \<wchar.h>|

## <a name="example"></a>Пример

Эта программа помещает системное время в целочисленную **aclock**, преобразует его в структуру **newtime** и затем преобразует его в строку для выходных данных, с помощью **asctime**функции.

```C
// crt_asctime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
    struct tm   *newTime;
    time_t      szClock;

    // Get time in seconds
    time( &szClock );

    // Convert time to struct tm form
    newTime = localtime( &szClock );

    // Print local time as a string.
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996
    // Note: asctime is deprecated; consider using asctime_s instead
}
```

```Output
Current date and time: Sun Feb 03 11:38:58 2002
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
