---
title: "Процедуры _ismbc | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ismbc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbc - процедуры"
  - "ismbc - процедуры"
ms.assetid: b8995391-7857-4ac3-9a1e-de946eb4464d
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Процедуры _ismbc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Каждая процедура **\_ismbc** проверяет определенный многобайтовый символ `c` на соответствие определенному условию.  
  
|||  
|-|-|  
|[\_ismbcalnum, \_ismbcalnum\_l, \_ismbcalpha, \_ismbcalpha\_l, \_ismbcdigit, \_ismbcdigit\_l](../Topic/_ismbcalnum,%20_ismbcalnum_l,%20_ismbcalpha,%20_ismbcalpha_l,%20_ismbcdigit,%20_ismbcdigit_l.md)|[\_ismbcl0, \_ismbcl0\_l, \_ismbcl1, \_ismbcl1\_l, \_ismbcl2, \_ismbcl2\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|  
|[\_ismbcgraph, \_ismbcgraph\_l, \_ismbcprint, \_ismbcprint\_l, \_ismbcpunct, \_ismbcpunct\_l, \_ismbcblank, \_ismbcblank\_l, \_ismbcspace, \_ismbcspace\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|[\_ismbclegal, \_ismbclegal\_l, \_ismbcsymbol, \_ismbcsymbol\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|  
|[\_ismbchira, \_ismbchira\_l, \_ismbckata, \_ismbckata\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|[\_ismbclower, \_ismbclower\_l, \_ismbcupper, \_ismbcupper\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|  
  
## Заметки  
 Результат проверки каждой процедуры **\_ismbc** зависит от действующей многобайтовой кодовой странице.  Многобайтовые кодовые страницы имеют однобайтовые буквенные символы.  По умолчанию многобайтовая кодовая страница имеет значение системной кодовой страницы ANSI по умолчанию, полученной от операционной системы при запуске программы.  Можно запросить или изменить использующуюся многобайтовую кодовую страницу с помощью [\_getmbcp](../c-runtime-library/reference/getmbcp.md) или [\_setmbcp](../c-runtime-library/reference/setmbcp.md) соответственно.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса **\_l** используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом **\_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  
  
|Подпрограмма|Условие теста|Пример кодовой страницы 932|  
|------------------|-------------------|---------------------------------|  
|[\_ismbcalnum, \_ismbcalnum\_l](../Topic/_ismbcalnum,%20_ismbcalnum_l,%20_ismbcalpha,%20_ismbcalpha_l,%20_ismbcdigit,%20_ismbcdigit_l.md)|Буквенно\-цифровой|Возвращает отличное от нуля значение, только если `c` \- однобайтовое представление английской буквы в ASCII: см. примеры для `_ismbcdigit` и `_ismbcalpha`.|  
|[\_ismbcalpha, \_ismbcalpha\_](../Topic/_ismbcalnum,%20_ismbcalnum_l,%20_ismbcalpha,%20_ismbcalpha_l,%20_ismbcdigit,%20_ismbcdigit_l.md)|Буквенный|Возвращает отличное от нуля значение, только если `c` \- однобайтовое представление английской буквы в ASCII: см. примеры для `_ismbcupper` и `_ismbclower`; или буква катакана: 0xA6\<\=`c`\<\=0xDF.|  
|[\_ismbcdigit, \_ismbcdigit\_l](../Topic/_ismbcalnum,%20_ismbcalnum_l,%20_ismbcalpha,%20_ismbcalpha_l,%20_ismbcdigit,%20_ismbcdigit_l.md)|Цифровой|Возвращает отличное от нуля значение, только если `c` \- однобайтовое представление цифры в ASCII: 0x30\<\=`c`\<\=0x39.|  
|[\_ismbcgraph, \_ismbcgraph\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Графика|Возвращает отличное от нуля значение только в том случае, если `c` — однобайтовое представление любого печатного символа ASCII или катаканы, за исключением пробела \( \).  См. примеры для `_ismbcdigit`, `_ismbcalpha` и `_ismbcpunct`.|  
|[\_ismbclegal, \_ismbclegal\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Допустимый многобайтовый символ|Возвращает отличный от нуля результат только если первый байт `c` содержится в диапазоне 0x81 — 0x9F или 0xE0 — 0xFC, а второй байт — в диапазон 0x40 — 0x7E или 0x80 — FC.|  
|[\_ismbclower, \_ismbclower\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Буква в нижнем регистре|Возвращает отличное от нуля значение только в том случае, если `c` \- однобайтовое представление буквы нижнего регистра английского алфавита в кодировке ASCII: 0x61\<\=`c`\<\=0x7A.|  
|[\_ismbcprint, \_ismbcprint\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Печатные|Возвращает отличное от нуля только в том случае, если `c` \- однобайтовое представление любого печатного символа ASCII или катакан, включая пробелы \( \). См. примеры для `_ismbcspace`, `_ismbcdigit`, `_ismbcalpha` и `_ismbcpunct`.|  
|[\_ismbcpunct, \_ismbcpunct\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Знак пунктуации|Возвращает отличное от нуля значение только в том случае, если `c` — однобайтовое представление любого знака препинания ASCII или катаканы.|  
|[\_ismbcblank, \_ismbcblank\_l,](../c-runtime-library/reference/ismbcgraph-functions.md)|Пробел или горизонтальная табуляция|Возвращает отличное от нуля только в том случае, если `c` \- однобайтовое представление пробельного символа или знака табуляции: `c`\=0x20 или `c`\=0x09.|  
|[\_ismbcspace, \_ismbcspace\_l](../c-runtime-library/reference/ismbcgraph-functions.md)|Whitespace|Возвращает отличное от нуля значение только в том случае, если `c` пробельный символ: `c`\=0x20 или 0x09\=\<`c`\<\=0x0D.|  
|[\_ismbcsymbol, \_ismbcsymbol\_l](../c-runtime-library/reference/ismbclegal-ismbclegal-l-ismbcsymbol-ismbcsymbol-l.md)|Многобайтовый символ|Возвращает отличный от нуля результат только если 0x8141\=\<`c`\<\=0x81AC.|  
|[\_ismbcupper, \_ismbcupper\_l](../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|Буква в верхнем регистре|Возвращает отличное от нуля значение только в том случае, если `c` \- однобайтовое представление буквы верхнего регистра английского алфавита в кодировке ASCII: 0x41\<\=`c`\<\=0x5A.|  
  
 **Специфичные для кодовой страницы 932**  
  
 Следующие процедуры зависят от кодовой страницы 932.  
  
|Подпрограмма|Условие теста \(только для кодовой страницы 932\)|  
|------------------|-------------------------------------------------------|  
|[\_ismbchira, \_ismbchira\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Двухбайтовая Хирагана: 0x829F\=\<`c`\<\=0x82F1.|  
|[\_ismbckata, \_ismbckata\_l](../c-runtime-library/reference/ismbchira-ismbchira-l-ismbckata-ismbckata-l.md)|Двухбайтовая катакана: 0x8340\=\<`c`\<\=0x8396.|  
|[\_ismbcl0, \_ismbcl0\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|Не Кандзи в формате JIS: 0x8140\=\<`c`\<\=0x889E.|  
|[\_ismbcl1, \_ismbcl1\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS уровня 1: 0x889F\=\<`c`\<\=0x9872.|  
|[\_ismbcl2, \_ismbcl2\_l](../c-runtime-library/reference/ismbcl0-ismbcl0-l-ismbcl1-ismbcl1-l-ismbcl2-ismbcl2-l.md)|JIS уровня 2: 0x989F\=\<`c`\<\=0xEA9E.|  
  
 `_ismbcl0`, `_ismbcl1` и `_ismbcl2` проверяют указанное значение `c` на соответствие условиям теста, описанным в предыдущей таблице, но не проверяют то, что `c` \- допустимый многобайтовый символ.  Если младший байт в диапазоне 0x00 – 0x3F, 0x7F, or 0xFD – 0xFF, то эти функции возвращают ненулевое значение, показывающее, что символ удовлетворяет условиям теста.  Используйте [\_ismbbtrail, \_ismbbtrail\_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md), чтобы проверить, определен ли многобайтовый символ.  
  
 **Конец раздела специфичных для кодовой страницы 932 функций**  
  
## См. также  
 [Классификация символов](../c-runtime-library/character-classification.md)   
 [Процедуры is, isw](../c-runtime-library/is-isw-routines.md)   
 [Процедуры \_ismbb](../c-runtime-library/ismbb-routines.md)