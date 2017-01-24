---
title: "_create_locale, _wcreate_locale | Microsoft Docs"
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
  - "_create_locale"
  - "__create_locale"
  - "_wcreate_locale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "create_locale"
  - "_create_locale"
  - "__create_locale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__create_locale - функция"
  - "_create_locale - функция"
  - "create_locale - функция"
  - "язык и региональные стандарты, создание"
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _create_locale, _wcreate_locale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает объект языкового стандарта.  
  
## Синтаксис  
  
```  
_locale_t _create_locale(  
   int category,  
   const char *locale   
);  
_locale_t _wcreate_locale(  
   int category,  
   const wchar_t *locale   
);  
```  
  
#### Параметры  
 `category`  
 Категория.  
  
 `locale`  
 Определитель языкового стандарта  
  
## Возвращаемое значение  
 Если предоставлены допустимые `locale` и `category`, возвращает указанные параметры языкового стандарта как объект `_locale_t`.  Не изменяет текущие параметры языкового стандарта программы.  
  
## Заметки  
 Функция `_create_locale` позволяет создать объект, который представляет некоторые зависящие от региона параметры, для использования в версиях, принимающих объект языкового стандарта, многих функций CRT \(функции с суффиксом `_l`\).  Поведение аналогично `setlocale`, за исключением того, что вместо применения указанных параметров языкового стандарта к текущей среде, параметры сохраняются в структуре `_locale_t`, которая затем возвращается.  Структура `_locale_t` должна быть освобождена с помощью [\_free\_locale](../../c-runtime-library/reference/free-locale.md), когда в ней больше нет необходимости.  
  
 `_wcreate_locale` — двухбайтовая версия `_create_locale`; аргумент `locale` для `_wcreate_locale` \- строка двухбайтовых знаков.  В остальных случаях поведение `_wcreate_locale` и `_create_locale` идентично.  
  
 Аргумент `category` задает поведение, зависящее от языкового стандарта, которое изменяется.  Флаги, используемые для `category`, и их влияние на части программы показаны в следующей таблице.  
  
 `LC_ALL`  
 Все категории, как показано ниже.  
  
 `LC_COLLATE`  
 Функции `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` и `wcsxfrm`.  
  
 `LC_CTYPE`  
 Функции обработки символов \(за исключением `isdigit`, `isxdigit`, `mbstowcs` и `mbtowc`\) не затрагиваются.  
  
 `LC_MONETARY`  
 Информация о форматировании валют возвращается функцией `localeconv`.  
  
 `LC_NUMERIC`  
 Символ десятичной запятой для процедур форматированного вывода данных \(например, `printf`\), процедур преобразования данных и для сведений о неденежном форматировании, возвращаемых `localeconv`.  Помимо символа десятичной запятой, `LC_NUMERIC` задает разделитель тысяч и строку управления группами, возвращаемую [localeconv](../../c-runtime-library/reference/localeconv.md).  
  
 `LC_TIME`  
 Функции `strftime` и `wcsftime`.  
  
 Эта функция проверяет параметры `category` и `locale`.  Если параметр категории не является одним из значений, указанных в предыдущей таблице, или если `locale` — `NULL`, функция возвращает `NULL`.  
  
 Аргумент `locale` — указатель на строку, которая задает языковой стандарт.  Дополнительные сведения о формате аргумента `locale` см. в разделе [Строки имени языкового стандарта, языка и страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).  
  
 Аргумент `locale` может принимать имя языкового стандарта, строковую переменную с названием языка, строковую переменную с названием языка и кодом страны\/региона, кодовую страницу, или строковую переменную с названием языка, код страны и кодовую страницу.  Набор доступных имен языкового стандарта, языков, кодов страны\/региона и кодовых страниц включает в себя те, которые поддерживаются API многоязыковой поддержки Windows, кроме кодовых страниц, требующие более двух байт на символ, например, UTF\-7 и UTF\-8.  Если указать кодовую страницу, подобную UTF\-7 или UTF\-8, `_create_locale` завершится ошибкой и вернет NULL.  Набор имен языкового стандарта, поддерживаемых `_create_locale`, описан в разделе [Строки имени языкового стандарта, языка и страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).  Набор строк языка и страны, поддерживаемых `_create_locale`, представлен в разделе [Строки языка](../../c-runtime-library/language-strings.md) и [Строки стран или регионов](../../c-runtime-library/country-region-strings.md).  
  
 Дополнительные сведения о параметрах языкового стандарта см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  
  
 Предыдущее название данной функции `__create_locale` \(с двумя символами подчеркивания в начале\) использовать не рекомендуется.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_create_locale`|\<locale.h\>|  
|`_wcreate_locale`|\<locale.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_create_locale.c  
// Sets the current locale to "de-CH" using the  
// setlocale function and demonstrates its effect on the strftime  
// function.  
  
#include <stdio.h>  
#include <locale.h>  
#include <time.h>  
  
int main(void)  
{  
       time_t ltime;  
       struct tm thetime;  
       unsigned char str[100];  
       _locale_t locale;  
  
       // Create a locale object representing the German (Switzerland) locale  
       locale = _create_locale(LC_ALL, "de-CH");  
       time (&ltime);  
       _gmtime64_s(&thetime, &ltime);  
  
       // %#x is the long date representation, appropriate to  
       // the current locale  
       //  
       if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
               printf("_strftime_l failed!\n");  
       else  
               printf("In de-CH locale, _strftime_l returns '%s'\n",   
                      str);  
  
       _free_locale(locale);  
  
       // Create a locale object representing the default C locale  
       locale = _create_locale(LC_ALL, "C");  
       time (&ltime);  
       _gmtime64_s(&thetime, &ltime);  
  
       if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
               printf("_strftime_l failed!\n");  
       else  
               printf("In 'C' locale, _strftime_l returns '%s'\n",   
                      str);  
  
       _free_locale(locale);  
}  
```  
  
## Пример результатов выполнения  
  
```  
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'  
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'  
```  
  
## Эквивалент в .NET Framework  
 [System::Globalization::CultureInfo Class](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)  
  
## См. также  
 [Строки имени языкового стандарта, языка и страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Строки языка](../../c-runtime-library/language-strings.md)   
 [Строки стран или регионов](../../c-runtime-library/country-region-strings.md)   
 [\_free\_locale](../../c-runtime-library/reference/free-locale.md)   
 [\_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../Topic/strlen,%20wcslen,%20_mbslen,%20_mbslen_l,%20_mbstrlen,%20_mbstrlen_l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, \_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)