---
title: "asctime, _wasctime | Microsoft Docs"
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
  - "_wasctime"
  - "asctime"
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
  - "_tasctime"
  - "asctime"
  - "_wasctime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tasctime - функция"
  - "_wasctime - функция"
  - "asctime - функция"
  - "tasctime - функция"
  - "преобразование структуры времени"
  - "время, преобразование"
  - "wasctime - функция"
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# asctime, _wasctime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразуют структуру времени `tm` в символьную строку.  Существуют более безопасные версии этих функций; см. раздел [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md).  
  
## Синтаксис  
  
```  
char *asctime(   
   const struct tm *timeptr   
);  
wchar_t *_wasctime(   
   const struct tm *timeptr   
);  
```  
  
#### Параметры  
 `timeptr`  
 Структура времени\/даты.  
  
## Возвращаемое значение  
 `asctime` возвращает указатель на результирующую символьную строку; `_wasctime` возвращает указатель на результирующую строку расширенных символов.  Нет какого\-либо возвращаемого значения ошибки.  
  
## Заметки  
 Существуют более безопасные версии этих функций; см. раздел [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md).  
  
 Функция `asctime` преобразует время, хранящееся в виде структуры, в символьную строку.  Значение `timeptr` обычно получается из вызова `gmtime` или `localtime`, обе из которых возвращают указатель на структуру `tm`, определенную в TIME.H.  
  
|Член timeptr|Значение|  
|------------------|--------------|  
|`tm_hour`|Часы после полуночи \(0–23\)|  
|`tm_isdst`|Положительно, если действует летнее время; 0 если летнее время не действует; отрицательно, если состояние летнего времени неизвестно.  Библиотека времени выполнения C принимает правила Соединенных Штатов для реализации проверки на летнее время \(DST\).|  
|`tm_mday`|День месяца \(1–31\)|  
|`tm_min`|Минуты после часа \(0–59\)|  
|`tm_mon`|Месяц \(0–11; Январь \= 0\)|  
|`tm_sec`|Секунды после минуты \(0–59\)|  
|`tm_wday`|День недели \(0–6; 0 \= воскресенье\)|  
|`tm_yday`|День года \(0–365; 1\-е января \= 0\)|  
|`tm_year`|Год \(текущий год минус 1900\)|  
  
 Преобразованная символьная строка также настраивается согласно параметрам зоны локального времени.  Сведения о настройке местного времени см. в разделах о функциях [time](../Topic/time,%20_time32,%20_time64.md), [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md), сведения об определении среды временной зоны и глобальных переменных см. функцию [\_tzset](../Topic/_tzset.md).  
  
 Итоговая строка, полученная с помощью `asctime`, содержит ровно 26 символов и имеет вид `Wed Jan 02 02:03:55 1980\n\0`.  Время в 24\-часовом формате.  Все поля имеют постоянную ширину.  Символ новой строки и нуль\-символ занимают две последние позиции строки.  `asctime` использует один статически выделенный буфер для хранения возвращаемой строки.  Каждый вызов этой функции уничтожает результат предыдущего вызова.  
  
 `_wasctime` — это версия `asctime` для расширенных символов.  В остальных случаях поведение `_wasctime` и `asctime` идентично.  
  
 Эти функции проверяют свои параметры.  Если `timeptr` указатель на null, или если он содержит значение вне допустимого диапазона, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение разрешено для продолжить, функция возвращает `NULL` и задает `errno` в `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tasctime`|`asctime`|`asctime`|`_wasctime`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`asctime`|\<time.h\>|  
|`_wasctime`|\<time.h\> или \<wchar.h\>|  
  
## Пример  
 Программа помещает системное время в целочисленную переменную `aclock`, преобразует его в структуру `newtime` и затем преобразует его в строку для вывода с помощью функции `asctime`.  
  
```  
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
  
  **Current date and time: Sun Feb 03 11:38:58 2002**   
## Эквивалент в .NET Framework  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)