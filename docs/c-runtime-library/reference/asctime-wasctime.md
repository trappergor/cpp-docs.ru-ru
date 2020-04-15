---
title: asctime, _wasctime
ms.date: 4/2/2020
api_name:
- _wasctime
- asctime
- _o__wasctime
- _o_asctime
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
ms.openlocfilehash: bda14f3b6046378ad23148371f354bb910163d3c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350484"
---
# <a name="asctime-_wasctime"></a>asctime, _wasctime

Преобразуйте структуру времени **тм** в строку символов. Существуют более безопасные версии этих функций; см. раздел [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

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

**asctime** возвращает указатель к результату строки персонажа; **_wasctime** возвращает указатель к результату строки широкого характера. Код ошибки не возвращается.

## <a name="remarks"></a>Remarks

Существуют более безопасные версии этих функций; см. раздел [asctime_s, _wasctime_s](asctime-s-wasctime-s.md).

Функция **asctime** преобразует время, хранящееся как структура, в строку символов. Значение *timeptr* обычно получено от звонока к **gmtime** или **локальное время**, которое оба возвращают указатель к структуре **tm,** определенной в ВРЕМЯ. H.

|Член timeptr|Значение|
|--------------------|-----------|
|**tm_hour**|Часы с полуночи (0-23)|
|**tm_isdst**|Положительно, если действует летнее время; 0 если летнее время не действует; отрицательно, если состояние летнего времени неизвестно. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST).|
|**tm_mday**|День месяца (1-31)|
|**tm_min**|Минуты за часом (0-59)|
|**tm_mon**|Месяц (0-11; Январь No 0)|
|**tm_sec**|Секунды за минутой (0-59)|
|**tm_wday**|День недели (0-6; Воскресенье No 0)|
|**Tm_yday**|День года (0-365; 1 января - 0)|
|**Tm_year**|Год (текущий год минус 1900)|

Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. Дополнительные сведения о настройке местного времени см. в описании функций [time](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md) и [localtime](localtime-localtime32-localtime64.md). Сведения об определении среды часового пояса и глобальных переменных см. в описании функции [_tzset](tzset.md).

Результат строки, производимый **asctime,** содержит ровно `Wed Jan 02 02:03:55 1980\n\0`26 символов и имеет форму. Время в 24-часовом формате. Все поля имеют постоянную ширину. Символ новой строки и нуль-символ занимают две последние позиции строки. **asctime** использует один, статично выделенный буфер для удержания строки возврата. Каждый вызов этой функции уничтожает результат предыдущего вызова.

**_wasctime** является широкохарактерным вариантом **asctime**. **_wasctime** и **asctime** ведут себя одинаково иначе.

Эти функции проверяют свои параметры. Если *timeptr* является нулевой указатель, или если он содержит вне диапазона значения, недействительный обработчик параметров вызывается, как описано в [параметре валидации.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функция возвращает **NULL** и устанавливает **errno** в **EINVAL.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

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

Эта программа помещает время системы в длиннее integer **aclock,** переводит его в структуру **newtime** и после этого преобразовывает его к форме шнура для выхода, используя функцию **asctime.**

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

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
