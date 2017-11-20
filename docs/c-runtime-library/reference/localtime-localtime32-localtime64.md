---
title: "localtime, _localtime32, _localtime64 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _localtime64
- _localtime32
- localtime
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
- localtime64
- _localtime64
- localtime32
- localtime
- _localtime32
dev_langs: C++
helpviewer_keywords:
- localtime32 function
- _localtime32 function
- _localtime64 function
- localtime64 function
- localtime function
- time, converting values
ms.assetid: 4260ec3d-43ee-4538-b998-402a282bb9b8
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b584d3e255bf3b2add52d5db00c6325b578ebf51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="localtime-localtime32-localtime64"></a>localtime, _localtime32, _localtime64
Преобразовывает значение времени и корректирует его для местного часового пояса. Доступны более безопасные версии этих функций; см. раздел [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct tm *localtime(  
   const time_t *timer   
);  
struct tm *_localtime32(  
   const __time32_t *timer  
);  
struct tm *_localtime64(  
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `timer`  
 Указатель на сохраненное время.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на результирующую структуру или значение `NULL`, если дата, переданная функции, удовлетворяет следующим условиям:  
  
-   До полуночи 1-го января 1970 года.  
  
-   После 03:14: 07 19 января 2038 года в формате UTC (при использовании функций `_time32` и `time32_t`).  
  
-   После 23:59:59 31-го декабря 3000 года в формате UTC (при использовании функций `_time64` и `__time64_t`).  
  
 Функция `_localtime64`, которая использует структуру `__time64_t`, допускает даты до 23:59:59 31 декабря 3000 года в формате UTC, тогда как функция `_localtime32` представляет даты до 23:59:59 18 января 2038 года в формате UTC.  
  
 `localtime` — подставляемая функция, эквивалентная функции `_localtime64`; функция `time_t` эквивалентна функции `__time64_t`. Если необходимо, чтобы компилятор принудительно интерпретировал `time_t` как старое 32-разрядное значение `time_t`, можно определить `_USE_32BIT_TIME_T`. В результате `localtime` будет вычисляться как `_localtime32`. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.  
  
 Поля структуры типа [tm](../../c-runtime-library/standard-types.md) хранят следующие значения, каждое из которых имеет тип `int`:  
  
 `tm_sec`  
 Секунды после минуты (0 - 59).  
  
 `tm_min`  
 Минуты после часа (0 - 59).  
  
 `tm_hour`  
 Часы после полуночи (0 - 23).  
  
 `tm_mday`  
 День месяца (1-31).  
  
 `tm_mon`  
 Месяц (0 – 11; Январь = 0).  
  
 `tm_year`  
 Год (текущий год минус 1900).  
  
 `tm_wday`  
 День недели (0 – 6; Воскресенье = 0).  
  
 `tm_yday`  
 День года (0 – 365; 1 января = 0).  
  
 `tm_isdst`  
 Положительное значение, если действует летнее время; 0, если летнее время не действует; отрицательное значение, если состояние летнего времени неизвестно. Если задана переменная среды `TZ`, для реализации перехода на летнее время (DST) в библиотеке времени выполнения C принимаются правила, подходящие для США.  
  
## <a name="remarks"></a>Примечания  
 Функция `localtime` преобразует время, хранящееся в виде значения [time_t](../../c-runtime-library/standard-types.md), и сохраняет результат в структуре типа `tm`. Значение `long` типа `timer` представляет секунды, прошедшие с полуночи (00:00:00) 1-го января 1970 года в формате UTC. Это значение обычно получается из функции `time`.  
  
 32- и 64-разрядные версии функций `gmtime`, `mktime`, `mkgmtime` и `localtime` используют для преобразования единственную для потока структуру `tm`. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова.  
  
 Функция `localtime` выполняет коррекцию для местного часового пояса, если пользователь сначала задает глобальную переменную среды `TZ`. Если переменная `TZ` задана, автоматически устанавливаются три других переменных среды (`_timezone`, `_daylight` и `_tzname`). Если переменная `TZ` не задана, функция `localtime` пытается использовать данные часового пояса, определенные в приложении Дата/время в Панели управления. Если эти сведения недоступны, по умолчанию используется значение PST8PDT, что означает тихоокеанский часовой пояс. Описание этих переменных см. в разделе [_tzset](../../c-runtime-library/reference/tzset.md). `TZ` представляет собой расширение Microsoft и не является частью стандарта ANSI для `localtime`.  
  
> [!NOTE]
>  Целевая среда должна попытаться определить, действует ли летнее время.  
  
 Эти функции проверяют свои параметры. Если параметр `timer` представляет собой указатель NULL или значение таймера отрицательно, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `NULL` и устанавливают параметр `errno` в значение `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`localtime`|\<time.h>|  
|`_localtime32`|\<time.h>|  
|`_localtime64`|\<time.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_localtime.cpp  
// compile with: /W3  
/* This program uses _time64 to get the current time   
 * and then uses localtime64() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm *newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
  
        _time64( &long_time );           // Get time as 64-bit integer.  
                                         // Convert to local time.  
        newtime = _localtime64( &long_time ); // C4996  
        // Note: _localtime64 deprecated; consider _localetime64_s  
  
        if( newtime->tm_hour > 12 )        // Set up extension.  
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime->tm_hour > 12 )        // Convert from 24-hour  
                newtime->tm_hour -= 12;    //   to 12-hour clock.  
        if( newtime->tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime->tm_hour = 12;  
  
        char buff[30];  
        asctime_s( buff, sizeof(buff), newtime );  
        printf( "%.19s %s\n", buff, am_pm );  
}  
```  
  
```Output  
Tue Feb 12 10:05:58 AM  
```  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)