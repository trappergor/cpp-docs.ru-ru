---
title: Языковой стандарт | Документы Майкрософт
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.international
dev_langs:
- C++
helpviewer_keywords:
- localization, locale
- country information
- language information routines
- setlocale function
- locale routines
ms.assetid: 442f8112-9288-44d7-be3c-15d22652093a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 638d4fbe6fd4dfce1fb3eeb246ef85c5b60fada0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="locale"></a>Языковой стандарт

*Языковой стандарт* — это настройки страны/региона и языковые настройки, с помощью которых можно настраивать программы. К числу категорий, зависящих от языкового стандарта, относится отображение форматов дат и денежных значений. Дополнительные сведения см. в разделе [Категории языковых стандартов](../c-runtime-library/locale-categories.md).

 Используйте функцию [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) для изменения или запроса некоторой или всей информации о языковом стандарте текущей программы или потока при использовании функций без суффикса **_l**. Функции с суффиксом **_l** используют переданные им параметры языкового стандарта только во время выполнения этой конкретной функции. Чтобы создать языковой стандарт для использования в функции с суффиксом **_l**, используйте функцию [_create_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md). Для освобождения этого языкового стандарта используйте функцию [_free_locale](../c-runtime-library/reference/free-locale.md). Чтобы получить текущий языковой стандарт, можно использовать функцию [_get_current_locale](../c-runtime-library/reference/get-current-locale.md).

 Используйте функцию [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) для управления тем, имеет ли каждый поток собственный языковой стандарт или все потоки в программе используют один и тот же языковой стандарт. Дополнительные сведения см. в разделе [Языковые стандарты и кодовые страницы](../text/locales-and-code-pages.md).

 Доступны более безопасные версии этих функций, в следующей таблице они отмечены суффиксом **_s** (secure, безопасная). Для получения дополнительной информации см. [Security Features in the CRT](../c-runtime-library/security-features-in-the-crt.md).

## <a name="locale-dependent-routines"></a>Зависимые от языковых стандартов подпрограммы

|Подпрограмма|Использовать|Зависимость настройки категории **setlocale**|
|-------------|---------|---------------------------------------------|
|[atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Преобразовать символ в значение с плавающей запятой|**LC_NUMERIC**|
|[atoi, _atoi_l, _wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Преобразовать символ в целочисленное значение|**LC_NUMERIC**|
|[_atoi64, _atoi64_l, _wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Преобразовать символ в 64-разрядное целочисленное значение|**LC_NUMERIC**|
|[atol, _atol_l, _wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Преобразовать символ в значение long|**LC_NUMERIC**|
|[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)|Преобразовать символ в значение double-long|**LC_NUMERIC**|
|[Подпрограммы is](../c-runtime-library/is-isw-routines.md)|Проверить данное целое число на указанное условие.|**LC_CTYPE**|
|[isleadbyte, _isleadbyte_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Проверить на старший байт|**LC_CTYPE**|
|[localeconv](../c-runtime-library/reference/localeconv.md)|Прочитать соответствующие значения для форматирования числовых величин|`LC_MONETARY, LC_NUMERIC`|
|[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)|Максимальная длина в байтах любого многобайтового символа текущего языкового стандарта (макрос, определенный в STDLIB.H)|**LC_CTYPE**|
|[_mbccpy, _mbccpy_l](../c-runtime-library/reference/mbccpy-mbccpy-l.md),[_mbccpy_s, _mbccpy_s_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|Скопировать один многобайтовый символ|**LC_CTYPE**|
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Проверить и вернуть количество байтов в многобайтовом символе|**LC_CTYPE**|
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Для строк многобайтовой кодировки: проверить каждый символ в строке; вернуть длину строки|**LC_CTYPE**|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md),[mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Преобразовать последовательность многобайтовых символов в соответствующую последовательность расширенных символов.|**LC_CTYPE**|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Преобразовать многобайтовый символ в соответствующий расширенный символ.|**LC_CTYPE**|
|Функции [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|Записать форматированные выходные данные|**LC_NUMERIC** (определяет вывод символа системы счисления)|
|Функции [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)|Прочитать форматированные входные данные|**LC_NUMERIC** (определяет распознавание символа системы счисления)|
|[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)|Выбрать языковой стандарт для программы|Неприменимо|
|[strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|Сравнить символы двух строк|**LC_COLLATE**|
|[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)|Сравнить две строки без учета регистра|**LC_CTYPE**|
|[_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|Сравнить символы двух строк (регистр не учитывается)|**LC_COLLATE**|
|[_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|Сравнить первые **n** символов двух строк|**LC_COLLATE**|
|[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)|Сравнить символы двух строк без учета регистра.|**LC_CTYPE**|
|[_strnicoll, _wcsnicoll, _mbsnicoll, _strnicoll_l, _wcsnicoll_l, _mbsnicoll_l](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Сравнить первые **n** символов двух строк (регистр не учитывается)|**LC_COLLATE**|
|[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)|Форматировать значение даты и времени в соответствии с предоставленным аргументом **format**|**LC_TIME**|
|[_strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md),[_strlwr_s, _strlwr_s_l, _mbslwr_s, _mbslwr_s_l, _wcslwr_s, _wcslwr_s_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|Преобразовать "на месте" каждую прописную букву в указанной строке в нижний регистр|**LC_CTYPE**|
|[strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Преобразовать строку символов в значение **double**|**LC_NUMERIC** (определяет распознавание символа системы счисления)|
|[strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Преобразовать строку символов в значение **long**|**LC_NUMERIC** (определяет распознавание символа системы счисления)|
|[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Преобразовать строку символов в значение unsigned long|**LC_NUMERIC** (определяет распознавание символа системы счисления)|
|[_strupr, _strupr_l, _mbsupr, _mbsupr_l, _wcsupr_l, _wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md),[_strupr_s, _strupr_s_l, _mbsupr_s, _mbsupr_s_l, _wcsupr_s, _wcsupr_s_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|Преобразовать "на месте" каждую букву в нижнем регистре в строке в верхний регистр|**LC_CTYPE**|
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Преобразовать строку в упорядоченную форму в соответствии с языковым стандартом|**LC_COLLATE**|
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md),[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Преобразовать указанный символ в соответствующий символ нижнего регистра|**LC_CTYPE**|
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md),[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Преобразовать указанный символ в соответствующую прописную букву|**LC_CTYPE**|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md),[wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Преобразовать последовательность расширенных символов в соответствующую последовательность многобайтовых символов|**LC_CTYPE**|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md),[wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Преобразовать расширенный символ в соответствующий многобайтовый символ|**LC_CTYPE**|

> [!NOTE]
> Для многобайтовых подпрограмм многобайтовая кодовая страница должна быть эквивалента языковому стандарту, установленному с помощью функции [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Функция [_setmbcp](../c-runtime-library/reference/setmbcp.md) с аргументом **_MB_CP_LOCALE** устанавливает многобайтовую кодовую страницу, совпадающую с кодовой страницей **setlocale**.

## <a name="see-also"></a>См. также

[Интернационализация](../c-runtime-library/internationalization.md)<br/>
 [Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
