---
title: "Интерпретация последовательностей в многобайтной кодировке | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.character.multibyte"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "MBCS [C++], кодовая страница языковых стандартов"
ms.assetid: da9150de-70ea-4d2f-90e6-ddb9202dd80b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Интерпретация последовательностей в многобайтной кодировке
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Большинство процедур, работающих с многобайтовыми символами, в библиотеке среды выполнения Майкрософт поддерживают последовательности многобайтовых символов, связанных с многобайтовой кодовой страницей.  Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  
  
### Многобайтовые процедуры, зависящие от языкового стандарта.  
  
|Подпрограмма|Применение|  
|------------------|----------------|  
|[\_mbclen, mblen, \_mblen\_l](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)|Проверить и вернуть количество байтов в многобайтовом символе|  
|[strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../Topic/strlen,%20wcslen,%20_mbslen,%20_mbslen_l,%20_mbstrlen,%20_mbstrlen_l.md)|Для строк многобайтовой кодировки: проверить каждый символ в строке; вернуть длину строки.  Для строк расширенных символов: вернуть длину строки.|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md), [mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Преобразовать последовательность многобайтовых символов в соответствующую последовательность расширенных символов.|  
|[mbtowc, \_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)|Преобразовать многобайтовый символ в соответствующий расширенный символ.|  
|[wcstombs, \_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md), [wcstombs\_s, \_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md)|Преобразуют последовательность расширенных символов в соответствующую последовательность многобайтовых символов|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md), [wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Преобразовать расширенный символ в соответствующий многобайтовый символ|  
  
## См. также  
 [Интернационализация](../c-runtime-library/internationalization.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)