---
title: Преобразование данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/21/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- c.conversions
dev_langs:
- C++
helpviewer_keywords:
- data conversion routines [C++]
- converting data
ms.assetid: b15b5268-7467-49f1-bf95-5299b598f94c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0260ebe37e0656f2078b247017d9f02ccc88474
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="data-conversion"></a>Преобразование данных

Эти процедуры позволяют преобразовывать данные из одной формы в другую. Обычно эти процедуры выполняются быстрее, чем создаваемые вами преобразования. Каждая подпрограмма, чье название содержит в начале префикс *to*, реализуется как функция и как макрос. Дополнительные сведения о выборе реализации см. в разделе [Рекомендации по выбору между функциями и макросами](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).

## <a name="data-conversion-routines"></a>Подпрограммы преобразования данных

|Подпрограмма|Использовать|
|-------------|---------|
|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Находит абсолютное значение целого числа|
|[atof, _atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Преобразуют строку в тип **float**|
|[atoi, _atoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Преобразуют строку в тип **int**|
|[_atoi64, _atoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Преобразуют строку в тип **__int64** или **long long**|
|[atol, _atol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Преобразуют строку в тип **long**|
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|Преобразуют символ UTF-16 или UTF-32 в эквивалентный многобайтовый символ|
|[_ecvt](../c-runtime-library/reference/ecvt.md), [_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|Преобразуют **double** в строку указанной длины|
|[_fcvt](../c-runtime-library/reference/fcvt.md), [_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|Преобразуют **double** в строку с указанным количеством цифр после запятой|
|[_gcvt](../c-runtime-library/reference/gcvt.md), [_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|Преобразуют число **double** в строку и сохраняют строку в буфер|
|[_itoa, _ltoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, ultow, _i64tow, _ui64tow](../c-runtime-library/reference/itoa-itow.md), [_itoa_s, _ltoa_s, _ultoa_s, _i64toa_s, _ui64toa_s, _itow_s, _ltow_s, _ultow_s, _i64tow_s, _ui64tow_s](../c-runtime-library/reference/itoa-s-itow-s.md)|Преобразуют целочисленные типы в строку|
|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Находят абсолютное значение целого числа типа **long**|
|[llabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Находят абсолютное значение целого числа типа **long long**|
|[_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)|Преобразуют однобайтовый многобайтовый символ в соответствующий двухбайтовый многобайтовый символ|
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|Преобразуют символ из стандарта Japan Industry Standard (JIS) в стандарт Japan Microsoft (JMS)|
|[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|Преобразуют символ из стандарта JMS в стандарт JIS|
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|Преобразуют многобайтовый символ в однобайтовый код хираганы|
|[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|Преобразуют многобайтовый символ в однобайтовый код катаканы|
|[_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)|Преобразуют двухбайтовый многобайтовый символ в соответствующий однобайтовый многобайтовый символ|
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Преобразуют многобайтовый символ в эквивалентный символ UTF-16 или UTF-32|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Преобразовать последовательность многобайтовых символов в соответствующую последовательность расширенных символов.|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Преобразовать многобайтовый символ в соответствующий расширенный символ.|
|[strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|Преобразуют строку в тип **double**|
|[strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|Преобразуют строку в целое число типа **long**|
|[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|Преобразуют строку в целое число без знака типа **unsigned long**|
|[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|Преобразуют строку в упорядоченную форму, основываясь на данных языкового стандарта|
|[toascii, __toascii](../c-runtime-library/reference/toascii-toascii.md)|Преобразуют символ в код ASCII||
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Проверяют символ и преобразуют его в нижний регистр, если это символ верхнего регистра|
|[tolower, _tolower, towlower, _tolower_l, _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)|Преобразуют символ в нижний регистр без дополнительных условий|[System::String::ToLower](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)|
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), [_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|Проверяют символ и преобразуют его в верхний регистр, если это символ нижнего регистра|
|[toupper, _toupper, towupper, _toupper_l, _towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|Преобразуют символ в верхний регистр без дополнительных условий|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Преобразовать последовательность расширенных символов в соответствующую последовательность многобайтовых символов|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Преобразовать расширенный символ в соответствующий многобайтовый символ|
|[_wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|Преобразуют строку расширенных символов в тип **double**|
|[_wtoi, _wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|Преобразуют строку расширенных символов в тип **int**|
|[_wtoi64, _wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|Преобразуют строку расширенных символов в тип **__int64** или **long long**|
|[_wtol, _wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|Преобразуют строку расширенных символов в тип **long**|

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
