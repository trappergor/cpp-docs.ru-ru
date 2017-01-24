---
title: "_strdate_s, _wstrdate_s | Microsoft Docs"
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
  - "_strdate_s"
  - "_wstrdate_s"
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
  - "_strdate_s"
  - "wstrdate_s"
  - "_wstrdate_s"
  - "strdate_s"
  - "_tstrdate_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "даты, копирование"
  - "Функция tstrdate_s"
  - "Функция wstrdate_s"
  - "Функция _tstrdate_s"
  - "Функция strdate_s"
  - "копирование дат"
  - "Функция _strdate_s"
  - "Функция _wstrdate_s"
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strdate_s, _wstrdate_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Копирование текущей системной даты в буфер.  Здесь представлены версии [\_strdate, \_wstrdate](../../c-runtime-library/reference/strdate-wstrdate.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _strdate_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrdate_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strdate_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrdate_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `buffer`  
 Указатель на буфер, который будет заполнен форматированной строкой даты.  
  
 \[входящий\] `numberOfElements`  
 Размер буфера.  
  
## Возвращаемое значение  
 Ноль, если успешно.  Возвращаемое значение — код ошибки в случае сбоя.  Коды ошибок определенны в ERRNO.H; см. таблицу ниже для конкретных ошибок, создаваемых этой функцией.  Дополнительные сведения о кодах ошибок см. в разделе [errno](../../c-runtime-library/errno-constants.md).  
  
## Условия возникновения ошибки  
  
|`buffer`|`numberOfElements`|Return|Содержимое `buffer`.|  
|--------------|------------------------|------------|--------------------------|  
|`NULL`|\(any\)|`EINVAL`|Без изменений|  
|Не `NULL` \(указывающий на допустимый буфер\)|0|`EINVAL`|Без изменений|  
|Не `NULL` \(указывающий на допустимый буфер\)|0 \< `numberOfElements` \< 9|`EINVAL`|Пустая строка|  
|Не `NULL` \(указывающий на допустимый буфер\)|`numberOfElements` \>\= 9|0|Текущая дата, отформатированная в соответствии с замечаниями|  
  
## Проблемы безопасности  
 Передача недопустимого отличного от `NULL` значения для буфера приведет к нарушению прав доступа, если параметр `numberOfElements` больше 9.  
  
 Передача для размера значения, превышающего фактический размер `buffer`, может привести к переполнению буфера.  
  
## Заметки  
 Эти функции предоставляют более безопасные версии `_strdate` и `_wstrdate`.  Функция `_strdate_s` копирует текущую системную дату в буфер, указанный в `buffer`, в формате `mm`\/`dd`\/`yy`, где `mm` — две цифры, представляющее месяц, `dd` — две цифры, представляющие день, и `yy` — две цифры последние две цифры года.  Например, строка `12/05/99` представляет 5\-е декабря 1999.  Буфер должен быть по крайней мере 9 знаков длиной.  
  
 `_wstrdate_s` — это двухбайтовая версия функции `_strdate_s`; аргумент и возвращаемое значение `_wstrdate_s` являются строками двухбайтовых символов.  В остальном эти функции ведут себя идентично.  
  
 Если `buffer` указатель на `NULL` или если `numberOfElements` менее 9 символов, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают \-1 и устанавливают `errno` в `EINVAL`, если буфер `NULL` или если `numberOfElements` меньше или равно 0, или устанавливают `errno` в `ERANGE` при `numberOfElements` меньше 9.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций:  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tstrdate_s`|`_strdate_s`|`_strdate_s`|`_wstrdate_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_strdate`|\<time.h\>|  
|`_wstrdate`|\<time.h\> или \<wchar.h\>|  
|`_strdate_s`|\<time.h\>|  
  
## Пример  
 См. пример для [time](../Topic/time,%20_time32,%20_time64.md).  
  
## Эквивалент в .NET Framework  
 [System::DateTime::Parse](https://msdn.microsoft.com/en-us/library/system.datetime.parse.aspx)  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)