---
title: "_strtime_s, _wstrtime_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wstrtime_s"
  - "_strtime_s"
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
  - "_wstrtime_s"
  - "strtime_s"
  - "wstrtime_s"
  - "_strtime_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strtime_s - функция"
  - "_wstrtime_s - функция"
  - "копирование времени в буферы"
  - "strtime_s - функция"
  - "время, копирование"
  - "wstrtime_s - функция"
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _strtime_s, _wstrtime_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Скопировать текущее время в буфер.  Здесь представлены версии [\_strtime, \_wstrtime](../Topic/_strtime,%20_wstrtime.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _strtime_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrtime_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strtime_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrtime_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `buffer`  
 Буфер, по крайней мере 10 байтов длиной, где будет записано время.  
  
 \[входящий\] `numberOfElements`  
 Размер буфера.  
  
## Возвращаемое значение  
 Ноль, если успешно.  
  
 Если возникает ошибочное условие, то вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Возвращаемое значение — код ошибки в случае сбоя.  Коды ошибок определенны в ERRNO.H; см. следующую таблицу для конкретных ошибок, создаваемых этой функцией.  Дополнительные сведения о кодах ошибок см. в разделе [Константы errno](../../c-runtime-library/errno-constants.md).  
  
### Условия возникновения ошибки  
  
|`buffer`|`numberOfElements`|Return|Содержимое `buffer`.|  
|--------------|------------------------|------------|--------------------------|  
|`NULL`|\(any\)|`EINVAL`|Без изменений|  
|Не `NULL` \(указывающий на допустимый буфер\)|0|`EINVAL`|Без изменений|  
|Не `NULL` \(указывающий на допустимый буфер\)|0 \< size \< 9|`EINVAL`|Пустая строка|  
|Не `NULL` \(указывающий на допустимый буфер\)|Size \> 9|0|Текущее время, отформатированное в соответствии с замечаниями|  
  
## Проблемы безопасности  
 Передача недопустимого, отличного от NULL значения для буфера приведет к нарушению прав доступа, если параметр `numberOfElements` больше 9.  
  
 Передача для `numberOfElements` значения, превышающего фактический размер буфера, может привести к переполнению буфера.  
  
## Заметки  
 Эти функции предоставляют более безопасные версии `_strtime` и `_wstrtime`.  Функция `_strtime_s` копирует текущее местное время в буфер, указанный в `timestr`*.* Время форматируется как `hh:mm:ss`, где `hh` является двумя цифрами, представляющими час в 24\-часовой записи, `mm` является двумя цифрами, представляющими минуты, прошедшие с последнего часа, и `ss` является двумя цифрами, представляющими секунды.  Например, строка `18:23:44` представляет 23 минуты и 44 секунды, прошедших с 18 часов. Буфер должен быть длиной, по крайней мере, 9 байт; фактический размер указывается в качестве второго параметра.  
  
 `_wstrtime` — это двухбайтовая версия функции `_strtime`; аргумент и возвращаемое значение `_wstrtime` являются строками двухбайтовых символов.  В остальном эти функции ведут себя идентично.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций:  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tstrtime_s`|`_strtime_s`|`_strtime_s`|`_wstrtime_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_strtime_s`|\<time.h\>|  
|`_wstrtime_s`|\<time.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// strtime_s.c  
  
#include <time.h>  
#include <stdio.h>  
  
int main()  
{  
    char tmpbuf[9];  
    errno_t err;  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    // Display operating system-style date and time.   
    err = _strtime_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
      exit(1);  
    }  
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );  
    err = _strdate_s( tmpbuf, 9 );  
    if (err)  
    {  
       printf("_strdate_s failed due to an invalid argument.");  
       exit(1);  
    }  
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );  
  
}  
```  
  
  **OS time:            14:37:49**  
**OS date:            04\/25\/03**   
## Эквивалент в .NET Framework  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)