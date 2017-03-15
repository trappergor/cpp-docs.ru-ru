---
title: "_strdate, _wstrdate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strdate"
  - "_wstrdate"
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
  - "_tstrdate"
  - "wstrdate"
  - "_wstrdate"
  - "_strdate"
  - "strdate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция strdate"
  - "даты, копирование"
  - "Функция tstrdate"
  - "Функция _wstrdate"
  - "Функция wstrdate"
  - "Функция _strdate"
  - "Функция _tstrdate"
  - "копирование дат"
ms.assetid: de8e4097-58f8-42ba-9dcd-cb4d9a9f1696
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# _strdate, _wstrdate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Копируют текущую системную дату в буфер.  Существуют более безопасные версии этих функций; см. раздел [\_strdate\_s, \_wstrdate\_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md).  
  
## Синтаксис  
  
```  
char *_strdate(  
   char *datestr   
);  
wchar_t *_wstrdate(  
   wchar_t *datestr   
);  
template <size_t size>  
char *_strdate(  
   char (&datestr)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wstrdate(  
   wchar_t (&datestr)[size]  
); // C++ only  
```  
  
#### Параметры  
 `datestr`  
 Указатель на буфер, содержащий форматированную строку даты.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает указатель на результирующую символьной строку `datestr`.  
  
## Заметки  
 Существуют более безопасные версии этих функций; см. раздел [\_strdate\_s, \_wstrdate\_s](../../c-runtime-library/reference/strdate-s-wstrdate-s.md).  Рекомендуется по возможности использовать более безопасные функции.  
  
 Функция `_strdate` копирует текущую системную дату в буфер, указанный в `datestr`, в формате `mm`\/`dd`\/`yy`, где `mm` — две цифры, представляющее месяц, `dd` — две цифры, представляющие день, и `yy` — две цифры последние две цифры года.  Например, строка `12/05/99` представляет 5\-е декабря 1999.  Буфер должен быть по крайней мере 9 байтов длиной.  
  
 Если параметр `datestr` указывает на `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, эти функции возвращают \-1 и устанавливают `errno` в значение `EINVAL`.  
  
 `_wstrdate` — это двухбайтовая версия функции `_strdate`; аргумент и возвращаемое значение `_wstrdate` являются строками двухбайтовых символов.  В остальном эти функции ведут себя идентично.  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tstrdate`|`_strdate`|`_strdate`|`_wstrdate`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_strdate`|\<time.h\>|  
|`_wstrdate`|\<time.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// strdate.c  
// compile with: /W3  
#include <time.h>  
#include <stdio.h>  
int main()  
{  
    char tmpbuf[9];  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    printf( "OS date: %s\n", _strdate(tmpbuf) ); // C4996  
    // Note: _strdate is deprecated; consider using _strdate_s instead  
}  
```  
  
  **OS date: 04\/25\/03**   
## Эквивалент в .NET Framework  
 [System::DateTime::Parse](https://msdn.microsoft.com/en-us/library/system.datetime.parse.aspx)  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [mktime, \_mktime32, \_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)