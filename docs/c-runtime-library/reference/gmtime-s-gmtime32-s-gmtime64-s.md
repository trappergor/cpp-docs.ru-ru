---
title: "gmtime_s, _gmtime32_s, _gmtime64_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gmtime32_s"
  - "gmtime_s"
  - "_gmtime64_s"
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
  - "_gmtime_s"
  - "gmtime64_s"
  - "gmtime32_s"
  - "_gmtime64_s"
  - "gmtime_s"
  - "_gmtime32_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gmtime_s - функция"
  - "gmtime32_s - функция"
  - "временные функции"
  - "gmtime64_s - функция"
  - "_gmtime64_s - функция"
  - "преобразование структуры времени"
  - "_gmtime_s - функция"
  - "_gmtime32_s - функция"
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# gmtime_s, _gmtime32_s, _gmtime64_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует значение времени в структуру. Здесь представлены версии функций [\_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t gmtime_s(  
   struct tm* _tm,  
   const __time_t* time  
);  
errno_t _gmtime32_s(  
   struct tm* _tm,  
   const __time32_t* time  
);  
errno_t _gmtime64_s(  
   struct tm* _tm,  
   const __time64_t* time   
);  
```  
  
#### Параметры  
 `_tm`  
 Указатель на структуру `tm`. Поля возвращаемой структуры содержат вычисленное значение аргумента `timer` в формате UTC, а не по местному времени.  
  
 `time`  
 Указатель на сохраненное время. Время представляется в виде секунд, истекших после полуночи \(00:00:00\) 1\-го января 1970 года, время в формате UTC.  
  
## Возвращаемое значение  
 Ноль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определены в файле Errno.h; список этих ошибок см. в разделе [errno](../../c-runtime-library/errno-constants.md).  
  
### Условия ошибок  
  
|`_tm`|`time`|Назад|Значение `_tm`|  
|-----------|------------|-----------|--------------------|  
|`NULL`|any|`EINVAL`|Не изменяется.|  
|Не `NULL` \(указывает на допустимый адрес в памяти\)|`NULL`|`EINVAL`|Во всех полях заданы значения –1.|  
|Не `NULL`|\< 0|`EINVAL`|Во всех полях заданы значения –1.|  
  
 В случае первых двух условий ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `EINVAL`.  
  
## Заметки  
 Функция `_gmtime32_s` разбирает значение `time` и сохраняет его в структуре типа `tm`, определенной в Time.h. Адрес структуры передается в параметре `_tm`. Значение `time` обычно получается из вызова функции `time`.  
  
> [!NOTE]
>  Целевая среда должна попытаться определить, действует ли летнее время. Библиотека времени выполнения C принимает правила США для реализации вычисления летнего времени.  
  
 Каждое из полей структуры имеет тип `int`, как показано в следующей таблице.  
  
 `tm_sec`  
 Секунды после минуты \(0–59\).  
  
 `tm_min`  
 Минуты после часа \(0–59\).  
  
 `tm_hour`  
 Часы после полуночи \(0–23\).  
  
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
 Всегда 0 для `gmtime`.  
  
 `_gmtime64_s`, которая использует `__time64_t` структуры, позволяет даты вверх до 23:59:59, 31 декабря 3000 года в формате UTC, тогда как `gmtime32_s` представляет даты только до 23:59:59 18 января 2038 года, UTC. Полночь 1\-го января 1970 года — нижняя граница диапазона дат для обеих функций.  
  
 `gmtime_s` — встроенная функция, которая принимает значение `_gmtime64_s`; функция `time_t` эквивалентна функции `__time64_t`. Если необходимо, чтобы компилятор принудительно интерпретировал `time_t` как старое 32\-разрядное значение `time_t`, можно определить `_USE_32BIT_TIME_T`. Это приведет к встраиванию `gmtime_s` в `_gmtime32_s`. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18\-го января 2038 года, и не поддерживается на 64\-разрядных платформах.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`gmtime_s`|\<time.h\>|  
|`_gmtime32_s`|\<time.h\>|  
|`_gmtime64_s`|\<time.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_gmtime64_s.c  
// This program uses _gmtime64_s to convert a 64-bit  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime_s to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm newtime;  
   __int64 ltime;  
   char buf[26];  
   errno_t err;  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:   
   err = _gmtime64_s( &newtime, &ltime );  
   if (err)  
   {  
      printf("Invalid Argument to _gmtime64_s.");  
   }  
  
   // Convert to an ASCII representation   
   err = asctime_s(buf, 26, &newtime);  
   if (err)  
   {  
      printf("Invalid Argument to asctime_s.");  
   }  
  
   printf( "Coordinated universal time is %s\n",   
           buf );  
}  
```  
  
```Output  
Coordinated universal time is Fri Apr 25 20:12:33 2003  
```  
  
## Эквивалент в .NET Framework  
  
-   [System::DateTime::UtcNow](https://msdn.microsoft.com/en-us/library/system.datetime.utcnow.aspx)  
  
-   [System::DateTime::ToUniversalTime](https://msdn.microsoft.com/en-us/library/system.datetime.touniversaltime.aspx)  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [\_mkgmtime, \_mkgmtime32, \_mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, \_mktime32, \_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)