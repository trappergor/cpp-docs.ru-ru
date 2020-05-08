---
title: gmtime, _gmtime32, _gmtime64
ms.date: 4/2/2020
api_name:
- _gmtime32
- gmtime
- _gmtime64
- _o__gmtime32
- _o__gmtime64
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- gmtime
- _gmtime32
- _gmtime64
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
ms.openlocfilehash: 16f4315837873c8d78065ea97a11188bdddedbed
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916241"
---
# <a name="gmtime-_gmtime32-_gmtime64"></a>gmtime, _gmtime32, _gmtime64

Преобразует значение времени **time_t** в структуру **TM** . Существуют более безопасные версии этих функций; см. раздел [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Синтаксис

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Параметры

*саурцетиме*<br/>
Указатель на хранимое время. Время представляется в виде секунд, истекших после полуночи (00:00:00) 1-го января 1970 года, время в формате UTC.

## <a name="return-value"></a>Возвращаемое значение

Указатель на структуру типа [tm](../../c-runtime-library/standard-types.md). Поля возвращаемой структуры содержат вычисленное значение аргумента *саурцетиме* в формате UTC, а не в местном времени. Каждое из полей структуры имеет тип **int**, как показано ниже.

|Поле|Описание|
|-|-|
|**tm_sec**|Секунд после минуты (0-59).|
|**tm_min**|Минут после часа (0-59).|
|**tm_hour**|Часы с полуночи (0-23).|
|**tm_mday**|День месяца (1-31).|
|**tm_mon**|Месяц (0-11; Январь = 0).|
|**tm_year**|Год (текущий год минус 1900).|
|**tm_wday**|День недели (0-6; Воскресенье = 0).|
|**tm_yday**|День года (0-365; 1 января = 0).|
|**tm_isdst**|Значение всегда равно 0 для **gmtime**.|

И 32-разрядные, и 64-разрядные версии **gmtime**, [функциях mktime](mktime-mktime32-mktime64.md), [мкгмтиме](mkgmtime-mkgmtime32-mkgmtime64.md)и [localtime](localtime-localtime32-localtime64.md) используют одну общую структуру **TM** для каждого потока для преобразования. Каждый вызов одной из этих функций уничтожает результат любого предыдущего вызова. Если *саурцетиме* представляет дату до полуночи 1 января 1970 г., **gmtime** возвращает **значение NULL**. Ошибка не возвращается.

**_gmtime64**, в котором используется структура **__time64_t** , позволяет выражать даты до 23:59:59, 31 декабря 3000, в формате utc, тогда как **_gmtime32** представляют даты только до 23:59:59 18 января 2038 года, UTC. Полночь 1-ого января 1970 года — нижняя граница диапазона дат для обеих функций.

**gmtime** — это встроенная функция, которая возвращает **_gmtime64**, а **time_t** эквивалентна **__time64_t** , если не определен **_USE_32BIT_TIME_T** . Если необходимо заставить компилятор интерпретировать **time_t** как старый 32-разрядный **time_t**, можно определить **_USE_32BIT_TIME_T**, но это приведет к тому, что **gmtime** будет встроен в **_gmtime32** и **time_t** быть определен как **__time32_t**. Рекомендуется не делать этого, поскольку данная возможность не поддерживается на 64-разрядных платформах и, в любом случае, ваше приложение может завершиться с ошибкой после 18-го января 2038 года.

Эти функции проверяют свои параметры. Если *саурцетиме* является пустым указателем или значение *саурцетиме* является отрицательным, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции возвращают **значение NULL** и **задают значение** **еинвал**.

## <a name="remarks"></a>Remarks

Функция **_gmtime32** разбивает значение *саурцетиме* и сохраняет его в статической выделенной структуре типа **TM**, определенной во времени. Высоты. Значение *саурцетиме* обычно получается из вызова функции [времени](time-time32-time64.md) .

> [!NOTE]
> В большинстве случаев целевая среда пытается определить, действует ли летнее время. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|---------------------|-|
|**gmtime**, **_gmtime32** **_gmtime64**|\<time.h>|\<CTime> или \<Time. h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_gmtime.c
// compile with: /W3
// This program uses _gmtime64 to convert a long-
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm *newtime;
   __int64 ltime;
   char buff[80];

   _time64( &ltime );

   // Obtain coordinated universal time:
   newtime = _gmtime64( &ltime ); // C4996
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s
   asctime_s( buff, sizeof(buff), newtime );
   printf( "Coordinated universal time is %s\n", buff );
}
```

```Output
Coordinated universal time is Tue Feb 12 23:11:31 2002
```

## <a name="see-also"></a>См. также раздел

[Операции управления временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
