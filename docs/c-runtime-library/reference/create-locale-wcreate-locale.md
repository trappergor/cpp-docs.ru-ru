---
title: "_create_locale, _wcreate_locale | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _create_locale
- __create_locale
- _wcreate_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- create_locale
- _create_locale
- __create_locale
dev_langs:
- C++
helpviewer_keywords:
- locales, creating
- _create_locale function
- create_locale function
- __create_locale function
ms.assetid: ca362464-9f4a-4ec6-ab03-316c55c5be81
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff6254ecd33dfc844108b76fc1644eff2a373aed
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="createlocale-wcreatelocale"></a>_create_locale, _wcreate_locale
Создает объект языкового стандарта.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `category`  
 Категория.  
  
 `locale`  
 Указатель языкового стандарта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если заданы допустимые значения `locale` и `category`, возвращает параметры указанного языкового стандарта как объект `_locale_t`. Текущие параметры языкового стандарта программы не изменяются.  
  
## <a name="remarks"></a>Примечания  
 Функция `_create_locale` позволяет создать объект, представляющий определенные параметры конкретного региона, для использования в локальных версиях многих функций CRT (функций с суффиксом `_l`). Она ведет себя так же, как `setlocale`, однако вместо применения указанных параметров языкового стандарта к текущей среде параметры сохраняются в возвращаемой структуре `_locale_t`. Когда структура `_locale_t` становится ненужной, ее необходимо освободить с помощью функции [_free_locale](../../c-runtime-library/reference/free-locale.md).  
  
 `_wcreate_locale` — это версия `_create_locale` с расширенными символами; аргумент `locale` для `_wcreate_locale` — строка расширенных символов. Поведение `_wcreate_locale` и `_create_locale` идентично в противном случае.  
  
 Аргумент `category` определяет соответствующие фрагменты поведения, связанные с локальным стандартом. Флаги, используемые для `category`, и части программы, которые они затрагивают, представлены в следующей таблице.  
  
 `LC_ALL`  
 Все категории, перечисленные ниже.  
  
 `LC_COLLATE`  
 Функции `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` и `wcsxfrm`.  
  
 `LC_CTYPE`  
 Функции обработки символов (за исключением `isdigit`, `isxdigit`, `mbstowcs` и `mbtowc`, которые не затрагиваются).  
  
 `LC_MONETARY`  
 Информация о форматировании денежных значений, возвращаемая функцией `localeconv`.  
  
 `LC_NUMERIC`  
 Символ десятичного разделителя для информации процедур форматированного вывода (например, `printf`), для процедур преобразования данных и для форматирования не относящихся к денежным значений, возвращаемой `localeconv`. Помимо символа десятичного разделителя `LC_NUMERIC` также задает разделитель тысяч и строку элемента управления группировкой, возвращаемую [localeconv](../../c-runtime-library/reference/localeconv.md).  
  
 `LC_TIME`  
 Функции `strftime` и `wcsftime`.  
  
 Эта функция проверяет параметры `category` и `locale`. Если параметр категории не является одним из значений, приведенных в предыдущей таблице, или `locale` имеет значение `NULL`, функция возвращает `NULL`.  
  
 Аргумент `locale` является указателем на строку, которая задает языковой стандарт. Дополнительные сведения о формате аргумента `locale` см. в разделе [Строки имени языкового стандарта, языка и страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md).  
  
 Аргумент `locale` может принимать имя языкового стандарта, строковую переменную с названием языка, строковую переменную с названием языка и код страны или региона, кодовую страницу или строковую переменную с названием языка, код страны или региона и кодовую страницу. Набор доступных имен языкового стандарта, названий языков, кодов страны и кодовых страниц включает все поддерживаемые API многоязыковой поддержки Windows, кроме кодовых страниц, требующих более 2 байт на один знак, например UTF-7 и UTF-8. Если указать кодовую страницу, такую как UTF-7 или UTF-8, `_create_locale` завершится ошибкой и вернет значение NULL. Набор имен языковых стандартов, поддерживаемых `_create_locale`, см. в разделе [Строки имени языкового стандарта, языка и страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Набор строковых значений языка и страны или региона, поддерживаемых `_create_locale`, представлен в разделах [Строки языка](../../c-runtime-library/language-strings.md) и [Строки страны или региона](../../c-runtime-library/country-region-strings.md).  
  
 Дополнительные сведения о региональных параметрах см. в разделе [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Предыдущее название этой функции, `__create_locale` (с двумя символами подчеркивания в начале), использовать не рекомендуется.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_create_locale`|\<locale.h>|  
|`_wcreate_locale`|\<locale.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```C  
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
    if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
    {
        printf("_strftime_l failed!\n");  
    }
    else  
    {
        printf("In de-CH locale, _strftime_l returns '%s'\n", str);  
    }
  
    _free_locale(locale);  
  
    // Create a locale object representing the default C locale  
    locale = _create_locale(LC_ALL, "C");  
    time(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    if (!_strftime_l((char *)str, 100, "%#x",   
                     (const struct tm *)&thetime, locale))  
    {
        printf("_strftime_l failed!\n");  
    }
    else  
    {
        printf("In 'C' locale, _strftime_l returns '%s'\n", str);  
    }
  
    _free_locale(locale);  
}  
```  
  
```Output  
In de-CH locale, _strftime_l returns 'Samstag, 9. Februar 2002'  
In 'C' locale, _strftime_l returns 'Saturday, February 09, 2002'  
```  
  
## <a name="see-also"></a>См. также  
 [Строки имени языкового стандарта, языка и страны и региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Строки языка](../../c-runtime-library/language-strings.md)   
 [Строки страны и региона](../../c-runtime-library/country-region-strings.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)   
 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)