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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: afa46e583437ebace8edd3a54a6d85e61e02854c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344100"
---
# <a name="gmtime-_gmtime32-_gmtime64"></a>gmtime, _gmtime32, _gmtime64

Преобразует **значение time_t** времени в структуру **тм.** Существуют более безопасные версии этих функций; см. раздел [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Синтаксис

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Параметры

*источникВремя*<br/>
Указатель на хранимое время. Время представляется в виде секунд, истекших после полуночи (00:00:00) 1-го января 1970 года, время в формате UTC.

## <a name="return-value"></a>Возвращаемое значение

Указатель на структуру типа [tm](../../c-runtime-library/standard-types.md). Поля возвращенной структуры удерживают оценочную стоимость аргумента *sourceTime* в UTC, а не в локальном времени. Каждое из полей структуры имеет тип **Int,** следующим образом:

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
|**tm_isdst**|Всегда 0 для **gmtime**.|

И 32-битные и 64-битные версии **gmtime,** [mktime,](mktime-mktime32-mktime64.md) [mkgmtime,](mkgmtime-mkgmtime32-mkgmtime64.md)и [локальное время](localtime-localtime32-localtime64.md) все используют одну общую структуру **тм** на поток для преобразования. Каждый вызов одной из этих функций уничтожает результат любого предыдущего вызова. Если *sourceTime* представляет дату до полуночи, 1 января 1970 года, **gmtime** возвращает **NULL**. Ошибка не возвращается.

**_gmtime64**, который использует **__time64_t** структуру, позволяет даты, которые будут выражены через 23:59:59, 31 декабря 3000, UTC, в то время как **_gmtime32** представляют даты только через 23:59:59 18 января 2038, UTC. Полночь 1-ого января 1970 года — нижняя граница диапазона дат для обеих функций.

**gmtime** является внеконечной функцией, которая оценивает **_gmtime64,** и **time_t** эквивалентно **__time64_t** если **_USE_32BIT_TIME_T** не определена. Если вы должны заставить компилятор интерпретировать **time_t** как старый 32-разрядный **time_t,** вы можете определить **_USE_32BIT_TIME_T,** но это приводит к **gmtime** быть в строже, чтобы **_gmtime32** и **time_t,** которые будут определены как **__time32_t**. Рекомендуется не делать этого, поскольку данная возможность не поддерживается на 64-разрядных платформах и, в любом случае, ваше приложение может завершиться с ошибкой после 18-го января 2038 года.

Эти функции проверяют свои параметры. Если *sourceTime* является нулевой указателем, или если значение *sourceTime* отрицательное, эти функции вызывают недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функции возвращают **NULL** и устанавливают **errno** **в EINVAL.**

## <a name="remarks"></a>Remarks

Функция **_gmtime32** разбивает значение *sourceTime* и хранит его в статично выделенной структуре типа **tm,** определяемой в TIME. H. Значение *sourceTime* обычно получено от вызова к функции [времени.](time-time32-time64.md)

> [!NOTE]
> В большинстве случаев целевая среда пытается определить, действует ли летнее время. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|---------------------|-|
|**gmtime**, **_gmtime32,** **_gmtime64**|\<time.h>|\<ctime> \<или time.h>|

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
