---
title: "localtime_s, _localtime32_s, _localtime64_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_localtime64_s"
  - "_localtime32_s"
  - "localtime_s"
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
  - "_localtime32_s"
  - "localtime32_s"
  - "localtime_s"
  - "localtime64_s"
  - "_localtime64_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция _localtime64_s"
  - "Функция localtime32_s"
  - "Функция _localtime32_s"
  - "Функция localtime64_s"
  - "время, преобразование значений"
  - "Функция localtime_s"
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# localtime_s, _localtime32_s, _localtime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует значение времени, а также исправляет для местного часового пояса. Здесь представлены версии функций [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t localtime_s(  
   struct tm* _tm,  
   const time_t *time   
);  
errno_t _localtime32_s(  
   struct tm* _tm,  
   const time32_t *time   
);  
errno_t _localtime64_s(  
   struct tm* _tm,  
   const _time64_t *time   
);  
```  
  
#### Параметры  
 `_tm`  
 Указатель на структуру времени заполнить.  
  
 `time`  
 Указатель на хранимое время.  
  
## Возвращаемое значение  
 Ноль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определены в файле Errno.h. Список этих ошибок см. в разделе [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
### Условия ошибок  
  
|`_tm`|`time`|Возвращаемое значение|Значение `_tm`|Вызывается обработчик недопустимого параметра|  
|-----------|------------|---------------------------|--------------------|---------------------------------------------------|  
|`NULL`|any|`EINVAL`|Без изменений|Да|  
|Не `NULL` \(указывает на допустимый адрес в памяти\)|`NULL`|`EINVAL`|Все поля задано значение \-1|Да|  
|Не `NULL` \(указывает на допустимый адрес в памяти\)|меньше 0 или больше `_MAX__TIME64_T`|`EINVAL`|Все поля задано значение \-1|Нет|  
  
 В случае первых двух условий ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `EINVAL`.  
  
## Заметки  
 Функция `_localtime32_s` преобразует время, хранящееся в виде значения [time\_t](../../c-runtime-library/standard-types.md), и сохраняет результат в структуре типа `tm`. Значение `long` типа `timer` представляет секунды, прошедшие с полуночи \(00:00:00\) 1\-го января 1970 года в формате UTC. Это значение обычно получается из функции `time`.  
  
 Функция `_localtime32_s` выполняет коррекцию для местного часового пояса, если пользователь сначала задает глобальную переменную среды `TZ`. Если переменная `TZ` задана, автоматически устанавливаются три других переменных среды \(`_timezone`, `_daylight` и `_tzname`\). Если переменная `TZ` не задана, функция `localtime32_s` пытается использовать данные часового пояса, определенные в приложении Дата\/время в Панели управления. Если не удается получить эту информацию, PST8PDT, что означает Тихоокеанский часовой пояс, используется по умолчанию. Описание этих переменных см. в разделе [\_tzset](../Topic/_tzset.md).`TZ` представляет собой расширение Microsoft и не является частью стандарта ANSI для `localtime`.  
  
> [!NOTE]
>  Целевая среда должна попытаться определить, действует ли летнее время.  
  
 `_localtime64_s`, которая использует `__time64_t` структуры, позволяет даты вверх до 23:59:59, 31 декабря 3000 года всемирного координированного времени \(UTC\), тогда как `_localtime32_s` представляет даты до 23:59:59 18 января 2038 года, UTC.  
  
 `localtime_s` — подставляемая функция, эквивалентная функции `_localtime64_s`; функция `time_t` эквивалентна функции `__time64_t`. Если необходимо, чтобы компилятор принудительно интерпретировал `time_t` как старое 32\-разрядное значение `time_t`, можно определить `_USE_32BIT_TIME_T`. В результате `localtime_s` будет вычисляться как `_localtime32_s`. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18\-го января 2038 года, и не поддерживается на 64\-разрядных платформах.  
  
 Поля структуры типа [tm](../../c-runtime-library/standard-types.md) хранят следующие значения, каждый из которых является `int`.  
  
 `tm_sec`  
 Секунды после минуты \(0–59\).  
  
 `tm_min`  
 Минуты после часа \(0–59\).  
  
 `tm_hour`  
 Часы после полуночи \(от 0 до 23\).  
  
 `tm_mday`  
 День месяца \(1–31\).  
  
 `tm_mon`  
 Месяц \(0–11; январь \= 0\).  
  
 `tm_year`  
 Год \(текущий год минус 1900\).  
  
 `tm_wday`  
 День недели \(0–6; воскресенье \= 0\).  
  
 `tm_yday`  
 День года \(0–365; 1\-е января \= 0\).  
  
 `tm_isdst`  
 Положительное значение, если действует летнее время; 0, если летнее время не действует; отрицательное значение, если состояние летнего времени неизвестно. Если `TZ` имеет значение переменной среды, библиотека времени выполнения C принимает правила, подходящие для США для реализации вычисления перехода на летнее время \(DST\).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`localtime_s`|\<time.h\>|  
|`_localtime32_s`|\<time.h\>|  
|`_localtime64_s`|\<time.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_localtime_s.c  
/* This program uses _time64 to get the current time   
 * and then uses _localtime64_s() to convert this time to a structure   
 * representing the local time. The program converts the result   
 * from a 24-hour clock to a 12-hour clock and determines the   
 * proper extension (AM or PM).  
 */  
  
#include <stdio.h>  
#include <string.h>  
#include <time.h>  
  
int main( void )  
{  
        struct tm newtime;  
        char am_pm[] = "AM";  
        __time64_t long_time;  
        char timebuf[26];  
        errno_t err;  
  
        // Get time as 64-bit integer.  
        _time64( &long_time );   
        // Convert to local time.  
        err = _localtime64_s( &newtime, &long_time );   
        if (err)  
        {  
            printf("Invalid argument to _localtime64_s.");  
            exit(1);  
        }  
        if( newtime.tm_hour > 12 )        // Set up extension.   
                strcpy_s( am_pm, sizeof(am_pm), "PM" );  
        if( newtime.tm_hour > 12 )        // Convert from 24-hour   
                newtime.tm_hour -= 12;    // to 12-hour clock.   
        if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.  
                newtime.tm_hour = 12;  
  
        // Convert to an ASCII representation.   
        err = asctime_s(timebuf, 26, &newtime);  
        if (err)  
        {  
           printf("Invalid argument to asctime_s.");  
           exit(1);  
        }  
        printf( "%.19s %s\n", timebuf, am_pm );  
}  
```  
  
## Пример результатов выполнения  
  
```  
Fri Apr 25 01:19:27 PM  
```  
  
## Эквивалент в .NET Framework  
 [System::DateTime::ToLocalTime](https://msdn.microsoft.com/en-us/library/system.datetime.tolocaltime.aspx)  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)