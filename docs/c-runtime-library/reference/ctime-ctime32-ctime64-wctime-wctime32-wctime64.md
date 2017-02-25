---
title: "ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ctime64"
  - "_wctime32"
  - "ctime"
  - "_wctime64"
  - "_ctime32"
  - "_wctime"
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
  - "_wctime64"
  - "_ctime32"
  - "_tctime"
  - "_wctime"
  - "_wctime32"
  - "_tctime64"
  - "_ctime64"
  - "ctime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция tctime64"
  - "Функция _ctime32"
  - "Функция ctime32"
  - "Функция _wctime"
  - "Функция wctime64"
  - "Функция _tctime64"
  - "Функция _tctime32"
  - "Функция _ctime64"
  - "Функция _wctime64"
  - "Функция ctime"
  - "Функция wctime32"
  - "Функция ctime64"
  - "Функция _wctime32"
  - "Функция _tctime"
  - "Функция tctime32"
  - "Функция tctime"
  - "Функция wctime"
  - "время, преобразование"
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразуют значение времени в строку и настраивают его в соответствии с параметрами локального часового пояса. Доступны более безопасные версии этих функций; в разделе [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).  
  
## Синтаксис  
  
```  
char *ctime(   
   const time_t *timer   
);  
char *_ctime32(   
   const __time32_t *timer )  
;  
char *_ctime64(   
   const __time64_t *timer )  
;  
wchar_t *_wctime(   
   const time_t *timer   
);  
wchar_t *_wctime32(   
   const __time32_t *timer  
);  
wchar_t *_wctime64(   
   const __time64_t *timer   
);  
```  
  
#### Параметры  
 `timer`  
 Указатель на сохраненное время.  
  
## Возвращаемое значение  
 Указатель на результирующую строку символов. Значение `NULL` возвращается в следующих случаях:  
  
-   `time` представляет дату перед полуночью 1\-го января 1970 года, в формате UTC.  
  
-   Если вы используете `_ctime32` или `_wctime32` и `time` представляет дату после 23:59:59 18 января 2038 года, UTC.  
  
-   Если используется функция `_ctime64` или `_wctime64` и `time` представляет дату после 23:59:59 31\-го декабря 3000 года \(в формате UTC\).  
  
 `ctime` — Встроенная функция, которая принимает значение `_ctime64` и `time_t` эквивалентно `__time64_t`. Если необходимо заставить компилятор интерпретирует `time_t` как старое 32\-разрядное `time_t`, можно определить `_USE_32BIT_TIME_T`. Это приведет `ctime` для вычисления `_ctime32`. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18\-го января 2038 года, и не поддерживается на 64\-разрядных платформах.  
  
## Заметки  
 Функция `ctime` преобразует значение времени, хранящееся в виде [time\_t](../../c-runtime-library/standard-types.md), в символьную строку. Значение `timer` обычно получается из вызова функции [time](../Topic/time,%20_time32,%20_time64.md), которая возвращает количество секунд, истекших после полуночи \(00:00: 00\) 1\-го января 1970 года \(в формате UTC\). Строка возвращаемого значения содержит ровно 26 символов и имеет следующий вид:  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 Время в 24\-часовом формате. Все поля имеют постоянную ширину. Символ новой строки \("\\n"\) и нуль\-символ \("\\0"\) занимают две последние позиции строки.  
  
 Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. Подробные сведения о настройке местного времени см. в описании функций `time`, [\_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) и [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md). Сведения об определении среды часового пояса и глобальных переменных см. в описании функции [\_tzset](../Topic/_tzset.md) .  
  
 Вызов функции `ctime` изменяет один статически выделенный буфер, используемый функциями `gmtime` и `localtime`. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова. Функция `ctime` делит статический буфер с функцией `asctime`. Таким образом, вызов функции `ctime` уничтожает результаты любого предыдущего вызова функций `asctime`, `localtime` или `gmtime`.  
  
 `_wctime` и `_wctime64` — версии функций `ctime` и `_ctime64` для расширенных символов; возвращают указатель на строку из расширенных символов. В остальном поведение функций `_ctime64`, `_wctime` и `_wctime64` совпадает с поведением функции `ctime`.  
  
 Эти функции проверяют свои параметры. Если `timer` является указателем null, или если значение таймера отрицательно, эти функции вызывают обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `NULL` и устанавливают параметр `errno` в значение `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`ctime`|\<time.h\>|  
|`_ctime32`|\<time.h\>|  
|`_ctime64`|\<time.h\>|  
|`_wctime`|\<time.h\> или \<wchar.h\>|  
|`_wctime32`|\<time.h\> или \<wchar.h\>|  
|`_wctime64`|\<time.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_ctime64.c  
// compile with: /W3  
/* This program gets the current  
 * time in _time64_t form, then uses ctime to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   __time64_t ltime;  
  
   _time64( &ltime );  
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996  
   // Note: _ctime64 is deprecated; consider using _ctime64_s  
}  
```  
  
```Output  
The time is Wed Feb 13 16:04:43 2002  
```  
  
## Эквивалент в .NET Framework  
  
-   [System::DateTime::GetDateTimeFormats](https://msdn.microsoft.com/en-us/library/system.datetime.getdatetimeformats.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)