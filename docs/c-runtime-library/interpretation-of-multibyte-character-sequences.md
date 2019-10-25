---
title: Интерпретация последовательностей многобайтовых символов
ms.date: 10/22/2019
f1_keywords:
- c.character.multibyte
helpviewer_keywords:
- MBCS [C++], locale code page
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
ms.openlocfilehash: 7431f0c63df60414af192ea38103318c775c430d
ms.sourcegitcommit: 0a5518fdb9d87fcc326a8507ac755936285fcb94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72811087"
---
# <a name="interpretation-of-multibyte-character-sequences"></a>Интерпретация последовательностей многобайтовых символов

Большинство подпрограмм для многобайтовых символов в библиотеке времени выполнения Microsoft распознают последовательности многобайтовых символов, относящиеся к многобайтовой кодовой странице. На выходное значение влияет параметр категории **LC_CTYPE** языкового стандарта. Дополнительные сведения см. в разделе [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для этого поведения, зависящего от языкового стандарта. Версии с суффиксом **_l** идентичны, за исключением того, что вместо текущего языкового стандарта используется параметр locale.

## <a name="locale-dependent-multibyte-routines"></a>Подпрограммы, зависящие от языкового стандарта

|Подпрограмма|Использовать|
|-------------|---------|
|[_mbclen, mblen, _mblen_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Проверить и вернуть количество байтов в многобайтовом символе|
|[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|Для строк многобайтовой кодировки: проверить каждый символ в строке и вернуть длину строки. Для строки расширенных символов: вернуть длину строки.|
|[mbstowcs, _mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs_s, _mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Преобразовать последовательность многобайтовых символов в соответствующую последовательность расширенных символов.|
|[mbtowc, _mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|Преобразовать многобайтовый символ в соответствующий расширенный символ.|
|[wcstombs, _wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md), [wcstombs_s, _wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|Преобразовать последовательность расширенных символов в соответствующую последовательность многобайтовых символов|
|[wctomb, _wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb_s, _wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Преобразовать расширенный символ в соответствующий многобайтовый символ|

## <a name="locale-independent-multibyte-routines"></a>Не зависящие от языкового стандарта подпрограммы

|Подпрограмма|Использовать|
|-------------|---------|
|[mbrtoc16, mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|Преобразование многобайтового кодировки UTF-8 в эквивалентный символ UTF-16 или UTF-32|
|[c16rtomb, c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|Преобразование символа UTF-16 или UTF-32 в эквивалентный многобайтовый символ UTF-8|

## <a name="see-also"></a>См. также

[Интернационализация](../c-runtime-library/internationalization.md)\
[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)
