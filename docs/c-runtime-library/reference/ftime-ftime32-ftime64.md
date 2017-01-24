---
title: "_ftime, _ftime32, _ftime64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ftime64"
  - "_ftime"
  - "_ftime32"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ftime32"
  - "_ftime"
  - "_ftime64"
  - "ftime64"
  - "ftime"
  - "ftime32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Функция ftime64"
  - "Функция _ftime64"
  - "текущее время"
  - "Функция _ftime"
  - "Функция ftime"
  - "Функция _ftime32"
  - "Функция ftime32"
  - "время, получение текущего"
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
caps.latest.revision: 27
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ftime, _ftime32, _ftime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получают текущее время.  Существуют более безопасные версии этих функций; см. раздел [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../Topic/_ftime_s,%20_ftime32_s,%20_ftime64_s.md).  
  
## Синтаксис  
  
```  
void _ftime(   
   struct _timeb *timeptr   
);  
void _ftime32(   
   struct __timeb32 *timeptr   
);  
void _ftime64(   
   struct __timeb64 *timeptr   
);  
```  
  
#### Параметры  
 `timeptr`  
 Указатель на структуру `_timeb`,`__timeb32` или `__timeb64`.  
  
## Заметки  
 Функция `_ftime` получает текущее местное время и сохраняет его в структуре, на которую указывает `timeptr`*.* Структуры `_timeb`, `__timeb32`,и`__timeb64` определены в SYS\\Timeb.h.  Они содержат четыре поля, которые перечислены в следующей таблице.  
  
 `dstflag`  
 Отлично от нуля, если в данный момент летнее время действует для этой зоны локального времени. \(См. [\_tzset](../Topic/_tzset.md) для объяснения способов определения летнего времени\).  
  
 `millitm`  
 Доли секунды в миллисекундах.  
  
 `time`  
 Время в секундах с полуночи \(00:00:00\), 1\-го января 1970, время в формате UTC.  
  
 `timezone`  
 Различие в минутах, при движении на запад, между временем в формате UTC и местным временем.  Значение `timezone` берётся из значения глобальной переменной `_timezone` \(см. `_tzset`\).  
  
 `_ftime64`, которая использует структуру `__timeb64`, разрешает даты создания файла до 23:59:59 31\-го декабря 3000, время в формате UTC; тогда как `_ftime32` представляет даты только до 03:14:07 19\-го января 2038, время в формате UTC.  Полночь 1\-ого января 1970 года \- нижняя граница диапазона дат для всех этих функций.  
  
 `_ftime` эквивалентна `_ftime64`, и `_timeb` содержит 64\-разрядное время.  Это является истинным, если не указано `_USE_32BIT_TIME_T`, в этом случае старая функциональность остается в силе; `_ftime` использует 32\-разрядное время, и `_timeb` содержит 32\-разрядное время.  
  
 `_ftime` проверяет свои параметры.  Если `timeptr` \- указатель на null, то функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может продолжено, функция задает `errno` значение `EINVAL`.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_ftime`|\<sys\/types.h\> и \<sys\/timeb.h\>|  
|`_ftime32`|\<sys\/types.h\> и \<sys\/timeb.h\>|  
|`_ftime64`|\<sys\/types.h\> и \<sys\/timeb.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
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
  
  **Seconds since midnight, January 1, 1970 \(UTC\): 1051553334**  
**Milliseconds: 230**  
**Minutes between UTC and local time: 480**  
**Daylight savings time flag \(1 means Daylight time is in effect\): 1**  
**The time is Mon Apr 28 11:08:54.230 2003**   
## Эквивалент в .NET Framework  
 [System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)