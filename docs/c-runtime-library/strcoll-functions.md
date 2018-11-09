---
title: Функции strcoll
ms.date: 11/04/2016
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- strcoll
helpviewer_keywords:
- code pages, using for string comparisons
- string comparison [C++], culture-specific
- strcoll functions
- strings [C++], comparing by code page
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
ms.openlocfilehash: c6b4b45184ea4cc3320f3de069884ac084c7cfcd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450236"
---
# <a name="strcoll-functions"></a>Функции strcoll

Каждая из функций `strcoll` и `wcscoll` сравнивает две строки согласно параметру категории `LC_COLLATE` кодовой страницы использующегося языкового стандарта. Каждая из функций `_mbscoll` сравнивает две строки в соответствии с использующейся многобайтовой кодовой страницей. Используйте функции `coll` для сравнения строк, когда есть различие между порядком символов в наборе и лексикографическим порядком символов в текущей кодовой странице и данное различие представляет интерес во время сравнения строк. Используйте соответствующие функции `cmp` для выполнения проверки только на равенство строк.

### <a name="strcoll-functions"></a>Функции strcoll

|однобайтовая кодировка|Юникод|MBCS|Описание:|
|----------|-------------|----------|-----------------|
|[strcoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|Сопоставить две строки|
|[_stricoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_wcsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|[_mbsicoll](../c-runtime-library/reference/stricoll-wcsicoll-mbsicoll-stricoll-l-wcsicoll-l-mbsicoll-l.md)|Сопоставить две строки (регистр не учитывается)|
|[_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|Сопоставить первые `count` символов двух строк|
|[_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Сопоставить первые `count` символов двух строк (регистр не учитывается)|

## <a name="remarks"></a>Примечания

Версии этих функций для однобайтовых символов (SBCS) (`strcoll`, `stricoll`, `_strncoll` и `_strnicoll`) сравнивают `string1` и `string2` согласно параметру категории `LC_COLLATE` текущего языкового стандарта. Эти функции отличаются от соответствующих функций `strcmp` тем, что функции `strcoll` используют сведения кодовой страницы языкового стандарта, предоставляющие последовательности сопоставления. Для сравнения строк в языковых стандартах, где порядок символов в наборе отличается от лексикографического порядка, функции `strcoll` необходимо использовать вместо соответствующих функций `strcmp`. Дополнительные сведения по `LC_COLLATE` см. в разделе [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).

Для некоторых кодовых страниц и соответствующих наборов символов порядок символов в наборе может отличаться от лексикографического порядка символов. Языковой стандарт "C" не входит в их число: порядок символов в кодировке ASCII совпадает с лексикографическим порядком символов. Однако, в некоторых европейских языковых стандартах, например, символ "a" (значение 0x61) предшествует символу "ä" (значение 0xE4) в кодировке, но "ä" предшествует символу "a" лексикографически. Чтобы выполнить лексикографическое сравнение в таком случае, используйте `strcoll` вместо `strcmp`. Также можно использовать функцию `strxfrm` для исходных строк, а затем использовать функцию `strcmp` для результирующих строк.

`strcoll`, `stricoll`, `_strncoll` и `_strnicoll` автоматически обрабатывают строки многобайтовых символов в соответствии с текущей кодовой страницей языкового стандарта, так же ведут себя их аналоги, работающие с расширенными (Юникод) символами. Версии этих функций, работающие с многобайтовыми символами (MBCS), однако, сопоставляют строки посимвольно согласно текущей многобайтовой кодовой странице.

Поскольку функции `coll` сопоставляют строки для лексикографического сравнения, тогда как функции `cmp` просто проверяют на равенство строк, функции `coll` гораздо медленнее, чем соответствующие версии `cmp`. Таким образом, функции `coll` следует использовать только в том случае, когда есть различие между порядком символов в наборе и лексикографическим порядке символов в текущей кодовой странице и данное различие представляет интерес во время сравнения строк.

## <a name="see-also"></a>См. также

[Языковой стандарт](../c-runtime-library/locale.md)<br/>
[Операции со строками](../c-runtime-library/string-manipulation-crt.md)<br/>
[localeconv](../c-runtime-library/reference/localeconv.md)<br/>
[_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[strcmp, wcscmp, _mbscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)