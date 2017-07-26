---
title: "Подпрограммы _ismbb | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _ismbb
- ismbb
dev_langs:
- C++
helpviewer_keywords:
- ismbb routines
- _ismbb routines
ms.assetid: d63c232e-3fe4-4844-aafd-2133846ece4b
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 0eb057f9d229c659f339f996d1ff38f65fd2e018
ms.openlocfilehash: 5f49afe582afad8aa01bf0aaaa1020d675ad7400
ms.contentlocale: ru-ru
ms.lasthandoff: 06/01/2017

---
# <a name="ismbb-routines"></a>Процедуры _ismbb
Проверяет заданное целочисленное значение `c` на выполнение определенного условия, используя текущий языковой стандарт или указанную категорию состояния преобразования LC_CTYPE.  
  
|||  
|-|-|  
|[_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|[_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|  
|[_ismbbalpha, _ismbbalpha_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|[_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|  
|[_ismbbblank, _ismbbblank_l](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|[_ismbblead, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|  
|[_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|[_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|  
|[_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|[_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|  
|[_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|[_ismbbtrail, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|  
  
## <a name="remarks"></a>Примечания  
 Каждая из подпрограмм семейства `_ismbb` проверяет заданное целочисленное значение `c` на выполнение определенного условия. Результат проверки зависит от действующей многобайтовой кодовой страницы. По умолчанию в качестве многобайтовой кодовая страницы установлена кодовая страница ANSI, полученная от операционной системы при запуске программы. Можно использовать [_getmbcp](../c-runtime-library/reference/getmbcp.md), чтобы запросить использующуюся в данный момент многобайтовую кодовую страницу, или [_setmbcp](../c-runtime-library/reference/setmbcp.md), чтобы изменить ее.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для этого зависящего от языкового стандарта поведения; версии с суффиксом **_l** идентичны им за тем исключением, что они используют переданный в них параметр языкового стандарта.  
  
 Подпрограммы семейства `_ismbb` проверяют заданное целое число `c` следующим образом.  
  
|Подпрограмма|Условие проверки байта|  
|-------------|-------------------------|  
|[_ismbbalnum](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum` &#124;&#124; `_ismbbkalnum`.|  
|[_ismbbalpha](reference/ismbbalpha-ismbbalpha-l.md)|`isalpha` &#124;&#124; `_ismbbkalnum`.|  
|[_ismbbblank](../c-runtime-library/reference/ismbbblank-ismbbblank-l.md)|`isblank`|  
|[_ismbbgraph](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|То же, что и `_ismbbprint`, но `_ismbbgraph` не включает символ пробела (0x20).|  
|[_ismbbkalnum](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Не входящий в набор ASCII текстовый символ, отличный от знака препинания. Например, только для кодовой страницы 932, функция `_ismbbkalnum` проверяет на принадлежность к алфавитно-цифровым символам катаканы.|  
|[_ismbbkana](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Катакана (0xA1–0xDF). Применяется только к кодовой странице 932.|  
|[_ismbbkprint](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|Не входящие в набор ASCII текстовые и пунктуационные символы. Например, только для кодовой страницы 932, `_ismbbkprint` проверяет на принадлежность к алфавитно-цифровым или пунктуационным символам катаканы (диапазон: 0xA1–0xDF).|  
|[_ismbbkpunct](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md)|Не входящий в набор ASCII знак препинания. Например, только для кодовой страницы 932, `_ismbbkpunct` проверяет на принадлежность к пунктуационным символам катаканы.|  
|[_ismbblead](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Первый байт многобайтового символа. Например, только для кодовой страницы 932, допустимые диапазоны: 0x81–0x9F, 0xE0–0xFC.|  
|[_ismbbprint](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint` &#124;&#124; `_ismbbkprint`. **ismbbprint** включает пробел (0x20).|  
|[_ismbbpunct](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct` &#124;&#124; `_ismbbkpunct`.|  
|[_ismbbtrail](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Второй байт многобайтового символа. Например, только для кодовой страницы 932, допустимые диапазоны: 0x40–0x7E, 0x80–0xEC.|  
  
 В следующей таблице приведены значения ORed, составляющие условия проверки для этих подпрограмм. Константы манифеста `_BLANK`, `_DIGIT`, `_LOWER`, `_PUNCT`и `_UPPER` определены в Ctype.h.  
  
|Подпрограмма|_BLANK|_DIGIT|LOWER|_PUNCT|UPPER|Не-<br /><br /> ASCII<br /><br /> текст|Не-<br /><br /> ASCII<br /><br /> punct|  
|-------------|-------------|-------------|-----------|-------------|-----------|------------------------------|-------------------------------|  
|`_ismbbalnum`|—|x|x|—|x|x|—|  
|`_ismbbalpha`|—|—|x|—|x|x|—|  
|`_ismbbblank`|x|—|—|—|—|—|—|  
|`_ismbbgraph`|—|x|x|x|x|x|x|  
|`_ismbbkalnum`|—|—|—|—|—|x|—|  
|`_ismbbkprint`|—|—|—|—|—|x|x|  
|`_ismbbkpunct`|—|—|—|—|—|—|x|  
|`_ismbbprint`|x|x|x|x|x|x|x|  
|`_ismbbpunct`|—|—|—|x|—|—|x|  
  
 Подпрограммы `_ismbb` реализованы и как функции, и как макросы. Дополнительные сведения о выборе любой реализации см. в разделе [Рекомендации по выбору между функциями и макросами](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация байтов](../c-runtime-library/byte-classification.md)   
 [Подпрограммы is, isw](../c-runtime-library/is-isw-routines.md)   
 [_mbbtombc, _mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)   
 [_mbctombb, _mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)
