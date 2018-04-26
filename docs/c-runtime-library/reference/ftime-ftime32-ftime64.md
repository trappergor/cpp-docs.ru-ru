---
title: _ftime, _ftime32, _ftime64 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _ftime64
- _ftime
- _ftime32
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
- _ftime32
- _ftime
- _ftime64
- ftime64
- ftime
- ftime32
dev_langs:
- C++
helpviewer_keywords:
- ftime64 function
- _ftime64 function
- current time
- _ftime function
- ftime function
- _ftime32 function
- ftime32 function
- time, getting current
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 027fd9e854a131eed35a473445bde8c881c02d40
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="ftime-ftime32-ftime64"></a>_ftime, _ftime32, _ftime64

Получает текущее время. Существуют более безопасные версии этих функций; см. раздел [_ftime_s, _ftime32_s, _ftime64_s](ftime-s-ftime32-s-ftime64-s.md).

## <a name="syntax"></a>Синтаксис

```C
void _ftime( struct _timeb *timeptr );
void _ftime32( struct __timeb32 *timeptr );
void _ftime64( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>Параметры

*timeptr* указатель **_timeb**, **__timeb32**, или **__timeb64** структуры.

## <a name="remarks"></a>Примечания

**_Ftime** функция получает текущее местное время и сохраняет его в структуре, на который указывает *timeptr*. **_Timeb**, **__timeb32**, и **__timeb64** структуры определяются в \<sys\\timeb.h >. Они содержат четыре поля, которые описываются в следующей таблице.

|Поле|Описание|
|-|-|
|**dstflag**|Ненулевое значение, если для местного часового пояса в данный момент действует летнее время. (Описание принципов определения летнего времени см. в разделе [_tzset](tzset.md).)|
|**millitm**|Доля секунды в миллисекундах.|
|**time**|Время представляется в виде числа секунд, истекших после полуночи (00:00:00) 1 января 1970 года, время в формате UTC.|
|**Часовой пояс**|Разница в минутах между временем UTC и местным временем при движении в западном направлении. Значение **часовой пояс** задать значение глобальной переменной **_timezone** (см. **_tzset**).|

**_Ftime64** функции, которая использует **__timeb64** структуры, позволяет даты создания файла можно выразить через 23:59:59, 31 декабря 3000 года, UTC, тогда как **_ftime32**только представляет даты до 23:59:59 18 января 2038 года, время UTC. Полночь 1 января 1970 года — нижняя граница диапазона дат для всех этих функций.

**_Ftime** функция эквивалентна **_ftime64**, и **_timeb** содержит 64-разрядное время, если не **_USE_32BIT_TIME_T** определен, в этом случае старое поведение действует; **_ftime** использует 32-разрядное время и **_timeb** содержит 32-разрядное время.

**_ftime** проверяет свои параметры. Если передается указатель null как *timeptr*, функция вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция устанавливает **errno** для **EINVAL**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_ftime**|\<sys/types.h> и \<sys/timeb.h>|
|**_ftime32**|\<sys/types.h> и \<sys/timeb.h>|
|**_ftime64**|\<sys/types.h> и \<sys/timeb.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_ftime.c
// compile with: /W3
// This program uses _ftime to obtain the current
// time and then stores this time in timebuffer.

#include <stdio.h>
#include <sys/timeb.h>
#include <time.h>

int main( void )
{
   struct _timeb timebuffer;
   char timeline[26];
   errno_t err;
   time_t time1;
   unsigned short millitm1;
   short timezone1;
   short dstflag1;

   _ftime( &timebuffer ); // C4996
   // Note: _ftime is deprecated; consider using _ftime_s instead

   time1 = timebuffer.time;
   millitm1 = timebuffer.millitm;
   timezone1 = timebuffer.timezone;
   dstflag1 = timebuffer.dstflag;

   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",
   time1);
   printf( "Milliseconds: %d\n", millitm1);
   printf( "Minutes between UTC and local time: %d\n", timezone1);
   printf( "Daylight savings time flag (1 means Daylight time is in "
           "effect): %d\n", dstflag1);

   err = ctime_s( timeline, 26, & ( timebuffer.time ) );
   if (err)
   {
       printf("Invalid argument to ctime_s. ");
   }
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,
           &timeline[20] );
}
```

```Output
Seconds since midnight, January 1, 1970 (UTC): 1051553334
Milliseconds: 230
Minutes between UTC and local time: 480
Daylight savings time flag (1 means Daylight time is in effect): 1
The time is Mon Apr 28 11:08:54.230 2003
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
