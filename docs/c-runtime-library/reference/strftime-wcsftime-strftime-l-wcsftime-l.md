---
title: "strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strftime"
  - "_wcsftime_l"
  - "_strftime_l"
  - "wcsftime"
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
  - "_tcsftime"
  - "strftime"
  - "wcsftime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_strftime_l - функция"
  - "strftime - функция"
  - "tcsftime - функция"
  - "_wcsftime_l - функция"
  - "wcsftime - функция"
  - "_tcsftime - функция"
  - "строки времени"
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# strftime, wcsftime, _strftime_l, _wcsftime_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Форматируют строку времени.  
  
## Синтаксис  
  
```  
size_t strftime(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr   
);  
size_t _strftime_l(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
size_t wcsftime(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr   
);  
size_t _wcsftime_l(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `strDest`  
 Выходная строка.  
  
 `maxsize`  
 Размер буфера `strDest`, измеренный в символах \(`char` или `wchart_t`\).  
  
 `format`  
 Строка управления форматом.  
  
 `timeptr`  
 структура данных `tm`  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 `strftime` возвращает количество символов в `strDest`, и `wcsftime` возвращает соответствующее количество расширенных символов.  
  
 Если общее количество символов, включая null в конце строки, больше `maxsize`, то и `strftime`, и `wcsftime` возвращают 0, и содержимое `strDest` не определено.  
  
 Количество символов в `strDest` равно числу строковых литералов в `format`, также, как все символы, которые могут быть добавлены в `format` через коды форматирования.  Символ null, завершающий строку, не учитывается в возвращаемом значении.  
  
## Заметки  
 Функции `strftime` и `wcsftime` форматируют значение времени `tm` в `timeptr` в соответствии с предоставленным аргументом `format` и сохраняют результат в буфере `strDest`*.* Максимум `maxsize` символов помещаются в строку.  Описание полей в структуре `timeptr` см. в разделе [asctime](../../c-runtime-library/reference/asctime-wasctime.md).  `wcsftime` \- эквивалент `strftime` для расширенных символов; её указывающий на строку аргумент указывает на строку из расширенных символов.  В остальном эти функции ведут себя идентично.  
  
> [!NOTE]
>  В версиях до Visual C\+\+ 2005 документация описывала параметр `format` функции `wcsftime` как имеющий тип данных `const wchar_t *`, но фактической реализацией типа данных `format` был `const char *`.  Реализация типа данных `format`была обновлена в соответствии с предыдущей и текущей документацией, то есть теперь это `const wchar_t *`.  
  
 Эта функция проверяет свои параметры.  Если `strDest`, `format` или `timeptr` указывают на null, или если структура данных `tm`, на которую указывает `timeptr`, недопустима \(например, если она содержит значения вне диапазона времени или даты\), или если строка `format` содержит недопустимый код форматирования, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает 0 и устанавливает `errno` в значение `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 Аргумент `format` состоит из одного или нескольких кодов; как в `printf`, коды форматирования начинаются знаком процента \(`%`\).  Символы, которые не начинаются с `%`, копируются неизмененными в `strDest`*.* Категория `LC_TIME` текущего языкового стандарта влияет на форматирование вывода `strftime`. \(Дополнительные сведения по `LC_TIME` см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).\) Функции без суффикса `_l` используют текущий языковой стандарт.  Версии этих функций с суффиксом `_l` идентичны за исключением того, что они принимают языковой стандарт в качестве параметра и используют его вместо текущего языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Коды форматирования для `strftime` перечислены ниже:  
  
 `%a`  
 Сокращенное название дня недели  
  
 `%A`  
 Полное название дня недели  
  
 `%b`  
 Сокращенное название месяца  
  
 `%B`  
 Полное название месяца  
  
 `%c`  
 Представление даты и времени, подходящее для языкового стандарта  
  
 `%d`  
 День месяца в виде десятичного числа \(01 \- 31\)  
  
 `%H`  
 Час в 24\-часовом формате \(00 \- 23\)  
  
 `%I`  
 Час в 12\-часовом формате \(01 \- 12\)  
  
 `%j`  
 День года как десятичное число \(001 — 366\)  
  
 `%m`  
 Месяц как десятичное число \(01 \- 12\)  
  
 `%M`  
 Минута как десятичное число \(00 \- 59\)  
  
 `%p`  
 Индикатор A.M.\/P.M. текущего языкового стандарта для 12\-часового формата  
  
 `%S`  
 Секунда как десятичное число \(00 — 59\)  
  
 `%U`  
 Неделя года как десятичное число, с воскресеньем в качестве первого дня недели \(00 — 53\)  
  
 `%w`  
 День недели как десятичное число \(0 \- 6; Воскресенье равно 0\)  
  
 `%W`  
 Неделя года как десятичное число, с понедельником в качестве первого дня недели \(00 — 53\)  
  
 `%x`  
 Представление дат для текущего языкового стандарта  
  
 `%X`  
 Представление времени для текущего языкового стандарта  
  
 `%y`  
 Год без века как десятичное число \(00 \- 99\)  
  
 `%Y`  
 Год с веком как десятичное число  
  
 `%z, %Z`  
 Либо название часового пояса, либо его аббревиатура, в зависимости от настроек реестра; отсутствие символов, если часовой пояс неизвестен  
  
 `%%`  
 Знак процента  
  
 Как в функции `printf`, флаг `#` может предшествовать любому коду форматирования.  В этом случае значение кода формата изменяется следующим образом.  
  
|Код формата|Значение|  
|-----------------|--------------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|Флаг `#` игнорируется.|  
|`%#c`|Представление полной даты и времени в соответствии с текущим языковым стандартом.  Например: "Tuesday, March 14, 1995, 12:41:29".|  
|`%#x`|Представление полной даты, соответствующее текущему языковому стандарту.  Например: "Tuesday, March 14, 1995".|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|Удаление лидирующих нулей \(если они есть\).|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strftime`|\<time.h\>|  
|`wcsftime`|\<time.h\> или \<wchar.h\>|  
|`_strftime_l`|\<time.h\>|  
|`_wcsftime_l`|\<time.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример для [time](../Topic/time,%20_time32,%20_time64.md).  
  
## Эквивалент в .NET Framework  
  
-   [System::DateTime::ToLongDateString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongdatestring.aspx)  
  
-   [System::DateTime::ToLongTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.tolongtimestring.aspx)  
  
-   [System::DateTime::ToShortDateString](https://msdn.microsoft.com/en-us/library/system.datetime.toshortdatestring.aspx)  
  
-   [System::DateTime::ToShortTimeString](https://msdn.microsoft.com/en-us/library/system.datetime.toshorttimestring.aspx)  
  
-   [System::DateTime::ToString](https://msdn.microsoft.com/en-us/library/system.datetime.tostring.aspx)  
  
## См. также  
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Управление временем](../../c-runtime-library/time-management.md)   
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)