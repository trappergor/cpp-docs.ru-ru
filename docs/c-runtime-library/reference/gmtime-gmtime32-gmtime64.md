---
title: gmtime, _gmtime32, _gmtime64 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
dev_langs:
- C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df2f7cc9f8bf6451ce8671b66c07fc5c3f06420d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64

Преобразует **time_t** значение для времени **tm** структуры. Существуют более безопасные версии этих функций; см. раздел [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Синтаксис

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Параметры

*sourceTime*<br/>
Указатель на хранимое время. Время представляется в виде секунд, истекших после полуночи (00:00:00) 1-го января 1970 года, время в формате UTC.

## <a name="return-value"></a>Возвращаемое значение

Указатель на структуру типа [tm](../../c-runtime-library/standard-types.md). Поля возвращаемой структуры содержат вычисленное значение *sourceTime* аргумент в формате UTC, а не в формате местного времени. Каждое из полей структуры имеет тип **int**, как показано ниже:

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
|**tm_isdst**|Всегда равно 0 для **gmtime**.|

32-разрядных и 64-разрядных версий из **gmtime**, [mktime](mktime-mktime32-mktime64.md), [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md), и [localtime](localtime-localtime32-localtime64.md) используют один общий **tm**  структуры на поток для преобразования. Каждый вызов одной из этих функций уничтожает результат любого предыдущего вызова. Если *sourceTime* представляет даты до полуночи 1 января 1970 года, **gmtime** возвращает **NULL**. Ошибка не возвращается.

**_gmtime64**, которая использует **__time64_t** структуры, включает даты можно выразить через 23:59:59, 31 декабря 3000 года, время в формате UTC, тогда как **_gmtime32** представляет даты только до 23:59:59 18 января 2038 года, UTC. Полночь 1-ого января 1970 года — нижняя граница диапазона дат для обеих функций.

**gmtime** — это встраиваемая функция, результатом которого является **_gmtime64**, и **time_t** эквивалентно **__time64_t** Если **_USE_32BIT_TIME_ T** определен. Если необходимо принудительно компилятор интерпретировать **time_t** как старое 32-разрядное **time_t**, можно определить **_USE_32BIT_TIME_T**, но это приводит к тому **gmtime** быть в **_gmtime32** и **time_t** как **__time32_t**. Рекомендуется не делать этого, поскольку данная возможность не поддерживается на 64-разрядных платформах и, в любом случае, ваше приложение может завершиться с ошибкой после 18-го января 2038 года.

Эти функции проверяют свои параметры. Если *sourceTime* является пустым указателем, или если *sourceTime* имеет отрицательное значение, эти функции вызывают обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, функции возвращают **NULL** и задайте **errno** для **EINVAL**.

## <a name="remarks"></a>Примечания

**_Gmtime32** разбивает функция *sourceTime* и сохраняет его в статически выделенной структуре типа **tm**, определенного времени. З. Значение *sourceTime* обычно получается из вызова [время](time-time32-time64.md) функции.

> [!NOTE]
> В большинстве случаев целевая среда пытается определить, действует ли летнее время. Библиотека времени выполнения C принимает правила США для реализации проверки на летнее время (DST).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|---------------------|-|
|**gmtime**, **_gmtime32**, **_gmtime64**|\<time.h>|\<CTime > или \<time.h >|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
