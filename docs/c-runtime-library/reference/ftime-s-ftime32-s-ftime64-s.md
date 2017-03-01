---
title: "_ftime_s, _ftime32_s, _ftime64_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftime_s
- _ftime64_s
- _ftime32_s
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
- _ftime_s
- _ftime64_s
- ftime_s
- _ftime32_s
- ftime32_s
- ftime64_s
dev_langs:
- C++
helpviewer_keywords:
- ftime32_s function
- ftime_s function
- _ftime64_s function
- current time
- ftime64_s function
- time, getting current
- _ftime_s function
- _ftime32_s function
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d6ff95a0d31d14de0941e5f8c3a3535fe0e5ee9c
ms.lasthandoff: 02/24/2017

---
# <a name="ftimes-ftime32s-ftime64s"></a>_ftime_s, _ftime32_s, _ftime64_s
Получает текущее время. Это версии функций [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _ftime_s(   
   struct _timeb *timeptr   
);  
errno_t _ftime32_s(   
   struct __timeb32 *timeptr   
);  
errno_t _ftime64_s(   
   struct __timeb64 *timeptr   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `timeptr`  
 Указатель на структуру `_timeb,``__timeb32` или `__timeb64`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль в случае успеха или код ошибки в случае неудачи. Если значение параметра `timeptr` равно `NULL`, возвращаемым значением является `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_ftime_s` получает текущее местное время и сохраняет его в структуре, на которую указывает `timeptr`*.* Структуры `_timeb,``__timeb32` и `__timeb64` определены в файле SYS\Timeb.h. Они содержат четыре поля, которые описываются в следующей таблице.  
  
 `dstflag`  
 Ненулевое значение, если для местного часового пояса в данный момент действует летнее время. (Описание принципов определения летнего времени см. в разделе [_tzset](../../c-runtime-library/reference/tzset.md).)  
  
 `millitm`  
 Доля секунды в миллисекундах.  
  
 `time`  
 Время представляется в виде числа секунд, истекших после полуночи (00:00:00) 1 января 1970 года, время в формате UTC.  
  
 `timezone`  
 Разница в минутах между временем UTC и местным временем при движении в западном направлении. Значение `timezone` задается на основе значения глобальной переменной `_timezone` (см. раздел `_tzset`).  
  
 Функция `_ftime64_s`, которая использует структуру `__timeb64`, поддерживает даты до 23:59:59 31 декабря 3000 года в формате UTC. При этом функция `_ftime32_s` представляет даты только до 23:59:59 18 января 2038 года в формате UTC. Полночь 1 января 1970 года — нижняя граница диапазона дат для всех этих функций.  
  
 Функция `_ftime_s` эквивалентна функции `_ftime64_s`, и `_timeb` содержит 64-разрядное время. Это верно, если не задана директива `USE_32BIT_TIME_T`, в противном случае действует старое поведение: функция \_`ftime_s` использует 32-разрядное время, и `_timeb` содержит 32-разрядное время.  
  
 Кроме того, функция `_ftime_s` проверяет свои параметры. Если в `timeptr` передан указатель NULL, функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_ftime_s`|\<sys/types.h> и \<sys/timeb.h>|  
|`_ftime32_s`|\<sys/types.h> и \<sys/timeb.h>|  
|`_ftime64_s`|\<sys/types.h> и \<sys/timeb.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_ftime64_s.c  
// This program uses _ftime64_s to obtain the current  
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
  
   _ftime64_s( &timebuffer );  
  
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
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 [System::DateTime::Now](https://msdn.microsoft.com/en-us/library/system.datetime.now.aspx)  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
