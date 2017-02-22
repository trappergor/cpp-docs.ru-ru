---
title: "Языковой стандарт | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "сведения о стране"
  - "подпрограммы обработки информации о языке"
  - "подпрограммы языковых стандартов"
  - "локализация, языковой стандарт"
  - "setlocale - функция"
ms.assetid: 442f8112-9288-44d7-be3c-15d22652093a
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Языковой стандарт
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*Языковой стандарт* относится к стране\/региону и языковым настройкам, с помощью которых можно настраивать программы.  К некоторым категориям, зависящим от языкового стандарта, относится отображение форматов дат и денежных значений.  Для получения дополнительной информации см. [Категории языковых стандартов](../c-runtime-library/locale-categories.md).  
  
 Используйте функцию [setlocale](../Topic/setlocale,%20_wsetlocale.md) для изменения или запроса некоторой или всей информации о языковом стандарте текущей программы или потока при использовании функций без суффикса `_l`.  Функции с суффиксом `_l` будут использовать параметры языкового стандарта, переданные как информация о языковом стандарте, во время выполнения этой конкретной функции.  Для создания языкового стандарта для использования в функции с суффиксом `_l`, используйте [\_create\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md).  Для освобождения этого языкового стандарта используйте [\_free\_locale](../c-runtime-library/reference/free-locale.md).  Чтобы получить текущий языковой стандарт, можно использовать [\_get\_current\_locale](../Topic/_get_current_locale.md).  
  
 Используйте [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) для управления тем, имеет ли каждый поток собственный языковой стандарт или все потоки в программе используют тот же языковой стандарт.  Дополнительные сведения см. в разделе [Языковые стандарты и кодовые страницы](../text/locales-and-code-pages.md).  
  
 Более безопасные версии функций доступны в следующей таблице, они отмечены суффиксом `_s` \(«безопасность»\).  Для получения дополнительной информации см. [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
### Зависимые от языковых стандартов процедуры  
  
|Подпрограмма|Применение|Зависимость параметров категории `setlocale`|  
|------------------|----------------|--------------------------------------------------|  
|[atof, \_atof\_l, \_wtof, \_wtof\_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Преобразовать символ в значение с плавающей точкой|`LC_NUMERIC`|  
|[atoi, \_atoi\_l, \_wtoi, \_wtoi\_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Преобразовать символ к целочисленному значению|`LC_NUMERIC`|  
|[\_atoi64, \_atoi64\_l, \_wtoi64, \_wtoi64\_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Преобразовать символ к 64\-разрядному целочисленному значению|`LC_NUMERIC`|  
|[atol, \_atol\_l, \_wtol, \_wtol\_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Преобразовать символ к значению long|`LC_NUMERIC`|  
|[\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Преобразовать символ к значению double\-long|`LC_NUMERIC`|  
|[is \- Процедуры](../c-runtime-library/is-isw-routines.md)|Проверить данное целое число на указанное условие.|`LC_CTYPE`|  
|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Проверить на старший байт|`LC_CTYPE`|  
|[localeconv](../c-runtime-library/reference/localeconv.md)|Прочитать соответствующие значения для форматирования числовых величин|`LC_MONETARY, LC_NUMERIC`|  
|[MB\_CUR\_MAX](../c-runtime-library/mb-cur-max.md)|Максимальная длина в байтах любого многобайтового символа текущего языкового стандарта \(макрос, определенный в STDLIB.H\)|`LC_CTYPE`|  
|[\_mbccpy, \_mbccpy\_l](../Topic/_mbccpy,%20_mbccpy_l.md),[\_mbccpy\_s, \_mbccpy\_s\_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|Скопировать один многобайтовый символ|`LC_CTYPE`|  
|[\_mbclen, mblen, \_mblen\_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Проверить и вернуть количество байтов в многобайтовом символе|`LC_CTYPE`|  
|[strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../Topic/strlen,%20wcslen,%20_mbslen,%20_mbslen_l,%20_mbstrlen,%20_mbstrlen_l.md)|Для строк многобайтовой кодировки: проверить каждый символ в строке; вернуть длину строки|`LC_CTYPE`|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md),[mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Преобразовать последовательность многобайтовых символов в соответствующую последовательность расширенных символов.|`LC_CTYPE`|  
|[mbtowc, \_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)|Преобразовать многобайтовый символ в соответствующий расширенный символ.|`LC_CTYPE`|  
|Функции [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|Записать форматированные выходные данные|`LC_NUMERIC` \(определяет вывод символа системы счисления\)|  
|Функции [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)|Прочитать форматированные входные данные|`LC_NUMERIC` \(определяет распознавание символа системы счисления\)|  
|[setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)|Выбрать языковой стандарт для программы|Неприменимо|  
|[strcoll, wcscoll, \_mbscoll, \_strcoll\_l, \_wcscoll\_l, \_mbscoll\_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|Сравнивают символы двух строк|`LC_COLLATE`|  
|[\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)|Сравнивают две строки без учета регистра|`LC_CTYPE`|  
|[\_stricoll, \_wcsicoll, \_mbsicoll, \_stricoll\_l, \_wcsicoll\_l, \_mbsicoll\_l](../Topic/_stricoll,%20_wcsicoll,%20_mbsicoll,%20_stricoll_l,%20_wcsicoll_l,%20_mbsicoll_l.md)|Сравнить символы двух строк \(регистр не учитывается\)|`LC_COLLATE`|  
|[\_strncoll, \_wcsncoll, \_mbsncoll, \_strncoll\_l, \_wcsncoll\_l, \_mbsncoll\_l](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|Сравнить первые `n` символов двух строк.|`LC_COLLATE`|  
|[\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)|Сравнить символы двух строк без учета регистра.|`LC_CTYPE`|  
|[\_strnicoll, \_wcsnicoll, \_mbsnicoll, \_strnicoll\_l, \_wcsnicoll\_l, \_mbsnicoll\_l](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Сравнить первые `n` символов двух строк \(регистр не учитывается\)|`LC_COLLATE`|  
|[strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Форматировать дату и значения времени в соответствии с предоставленным аргументом `format`|`LC_TIME`|  
|[\_strlwr, \_wcslwr, \_mbslwr, \_strlwr\_l, \_wcslwr\_l, \_mbslwr\_l](../Topic/_strlwr,%20_wcslwr,%20_mbslwr,%20_strlwr_l,%20_wcslwr_l,%20_mbslwr_l.md),[\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|Преобразовать "на месте" каждую прописную букву в указанной строке в нижний регистр|`LC_CTYPE`|  
|[strtod, \_strtod\_l, wcstod, \_wcstod\_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Преобразовать строку символов в значение `double`|`LC_NUMERIC` \(определяет распознавание символа системы счисления\)|  
|[strtol, wcstol, \_strtol\_l, \_wcstol\_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Преобразовать строку символов в значение `long`|`LC_NUMERIC` \(определяет распознавание символа системы счисления\)|  
|[strtoul, \_strtoul\_l, wcstoul, \_wcstoul\_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Преобразовать строку символов в значение unsigned long|`LC_NUMERIC` \(определяет распознавание символа системы счисления\)|  
|[\_strupr, \_strupr\_l, \_mbsupr, \_mbsupr\_l, \_wcsupr\_l, \_wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md),[\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|Преобразовать "на месте" каждую букву в нижнем регистре в строке в прописную|`LC_CTYPE`|  
|[strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Преобразовать строку в упорядоченную форму в соответствии с языковым стандартом|`LC_COLLATE`|  
|[tolower, \_tolower, towlower, \_tolower\_l, \_towlower\_l](../Topic/tolower,%20_tolower,%20towlower,%20_tolower_l,%20_towlower_l.md),[\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Преобразовать данный символ в соответствующий символ нижнего регистра|`LC_CTYPE`|  
|[toupper, \_toupper, towupper, \_toupper\_l, \_towupper\_l](../Topic/toupper,%20_toupper,%20towupper,%20_toupper_l,%20_towupper_l.md),[\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Преобразовать данный символ в соответствующую прописную букву|`LC_CTYPE`|  
|[wcstombs, \_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md),[wcstombs\_s, \_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md)|Преобразуют последовательность расширенных символов в соответствующую последовательность многобайтовых символов|`LC_CTYPE`|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md),[wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Преобразовать расширенный символ в соответствующий многобайтовый символ|`LC_CTYPE`|  
  
> [!NOTE]
>  Для многобайтовых процедур многобайтовая кодовая страница должна быть эквивалента языковому стандарту, установленному с помощью [setlocale](../Topic/setlocale,%20_wsetlocale.md).  [\_setmbcp](../c-runtime-library/reference/setmbcp.md) с аргументом `_MB_CP_LOCALE` делает многобайтовую кодовую страницу совпадающей с кодовой страницей `setlocale`.  
  
## См. также  
 [Интернационализация](../c-runtime-library/internationalization.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)