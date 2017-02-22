---
title: "Классификация байтов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.types.bytes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "процедуры классификации байтов"
  - "байты, проверка"
  - "кодовая страница 932"
ms.assetid: 1cb52d71-fb0c-46ca-aad7-6472c1103370
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Классификация байтов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Каждая из этих процедур проверяет указанный байт многобайтового символа на соответствие условию.  Если не указано иное, выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  
  
> [!NOTE]
>  По определению символы между 0 и 127 кодировки ASCII являются подмножеством всех многобайтовых кодировок.  Например, японская кодировка катакана содержит как символы ASCII, так и другие символы.  
  
 Предопределенные константы в следующей таблице определены в CTYPE.H.  
  
### Подпрограммы классификации байтов многобайтовых символов  
  
|Подпрограмма|Условие проверки байта|Эквивалент в .NET Framework|  
|------------------|----------------------------|---------------------------------|  
|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|Старший байт; результат теста зависит от значения категории `LC_CTYPE` текущего языкового стандарта|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbalnum, \_ismbbalnum\_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md)|`isalnum &#124;&#124; _ismbbkalnum`|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbalpha, \_ismbbalpha\_l](../c-runtime-library/reference/ismbbalpha-ismbbalpha-l.md)|`isalpha &#124;&#124; _ismbbkalnum`|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbgraph, \_ismbbgraph\_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md)|То же, что и `_ismbbprint`, но `_ismbbgraph` не содержит символ пробела \(0x20\)|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbkalnum, \_ismbbkalnum\_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md)|Не входящий в набор ASCII символ, отличный от знака препинания.  Например, только для кодовой страницы 932, `_ismbbkalnum` проверяет на алфавитно\-цифровой символ катаканы|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbkana, \_ismbbkana\_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md)|Катакана \(0xA1 – 0xDF\), только для кодовой страницы 932|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbkprint, \_ismbbkprint\_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md)|Не входящие в набор ASCII текстовые и пунктуационные символы.  Например, только для кодовой страницы 932, `_ismbbkprint` проверяет на алфавитно\-цифровой или пунктуационный символ катаканы \(диапазон: 0xA1 – 0xDF\).|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbkpunct, \_ismbbkpunct\_l](../Topic/_ismbbkpunct,%20_ismbbkpunct_l.md)|Не входящий в набор ASCII знак препинания.  Например, только для кодовой страницы 932, `_ismbbkpunct` проверяет на пунктуационный символ катаканы.|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbblead, \_ismbblead\_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md)|Первый байт многобайтового символа.  Например, только для кодовой страницы 932, допустимые диапазоны: 0x81 – 0x9F, 0xE0 – 0xFC.|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbprint, \_ismbbprint\_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md)|`isprint &#124;&#124; _ismbbkprint. ismbbprint` содержит символ пробела \(0x20\)|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbpunct, \_ismbbpunct\_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md)|`ispunct &#124;&#124; _ismbbkpunct`|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbbtrail, \_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md)|Второй байт многобайтового символа.  Например, только для кодовой страницы 932, допустимые диапазоны: 0x40 – 0x7E, 0x80 – 0xEC.|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_ismbslead, \_ismbslead\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Старший байт \(в контексте строк\)|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[ismbstrail, \_ismbstrail\_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)|Младший байт \(в контексте строк\)|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_mbbtype, \_mbbtype\_l](../c-runtime-library/reference/mbbtype-mbbtype-l.md)|Возвращает тип байта, основываясь на предыдущем байте|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[\_mbsbtype, \_mbsbtype\_l](../c-runtime-library/reference/mbsbtype-mbsbtype-l.md)|Возвращает тип байта в строке|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
|[mbsinit](../c-runtime-library/reference/mbsinit.md)|Отслеживает состояние преобразования многобайтового символа.|Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)|  
  
 Макрос `MB_LEN_MAX`, определенный в LIMITS.H, разворачивается в максимальную длину в байтах, которую может иметь любой многобайтовый символ.  `MB_CUR_MAX`, определенный в STDLIB.H, разворачивается в максимальную длину в байтах любого многобайтового символа текущего языкового стандарта.  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)