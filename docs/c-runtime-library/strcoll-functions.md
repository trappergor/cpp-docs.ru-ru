---
title: "Функции strcoll | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strcoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "кодовые страницы, использование для сравнений строк"
  - "strcoll - функции"
  - "сравнение строк [C++], зависящие от языка и региональных параметров"
  - "строки [C++], сравнение по кодовой странице"
ms.assetid: c09eeff3-8aba-4cfb-a524-752436d85573
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Функции strcoll
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Каждая из функций `strcoll` и `wcscoll` сравнивает две строки согласно параметру категории `LC_COLLATE` кодовой страницы использующегося языкового стандарта.  Каждая из функций `_mbscoll` сравнивает две строки в соответствии с использующейся многобайтовой кодовой страницей.  Используйте функции `coll` для сравнения строк, когда есть различие между порядком символов в наборе и лексикографическим порядке символов в текущей кодовой странице и данное различие представляет интерес во время сравнения строк.  Используйте соответствующие функции `cmp` для выполнения проверки только на равенство строк.  
  
### Функции strcoll  
  
|однобайтовая кодировка|Юникод|MBCS|Описание|  
|----------------------------|------------|----------|--------------|  
|[strcoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[wcscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|[\_mbscoll](../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)|Сравнить две строки|  
|[\_stricoll](../Topic/_stricoll,%20_wcsicoll,%20_mbsicoll,%20_stricoll_l,%20_wcsicoll_l,%20_mbsicoll_l.md)|[\_wcsicoll](../Topic/_stricoll,%20_wcsicoll,%20_mbsicoll,%20_stricoll_l,%20_wcsicoll_l,%20_mbsicoll_l.md)|[\_mbsicoll](../Topic/_stricoll,%20_wcsicoll,%20_mbsicoll,%20_stricoll_l,%20_wcsicoll_l,%20_mbsicoll_l.md)|Сравнить две строки \(регистр не учитывается\)|  
|[\_strncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[\_wcsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|[\_mbsncoll](../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|Сравнить первые `count` символов двух строк.|  
|[\_strnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[\_wcsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|[\_mbsnicoll](../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|Сравнить первые `count` символов двух строк \(регистр не учитывается\)|  
  
## Заметки  
 Версии этих функций для однобайтовых символов \(SBCS\) \(`strcoll`, `stricoll`, `_strncoll` и `_strnicoll`\) сравнивают `string1` и `string2` согласно параметру категории `LC_COLLATE` текущего языкового стандарта.  Эти функции зависят от соответствующих функций `strcmp`, так как `strcoll` используют сведения кодовой страницы языкового стандарта, предоставляющие упорядоченные последовательности.  Для сравнения строк в языковых стандартах, где порядок символов в наборе отличается от лексикографического порядка, функции `strcoll` должны использоваться вместо соответствующей функции `strcmp`.  Дополнительные сведения по `LC_COLLATE` см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  
  
 Для некоторых кодовых страниц и соответствующих наборов символов порядок символов в наборе может отличаться от лексикографического порядка символов.  Языковой стандарт "C" не входит в их число: порядок символов в кодировке ASCII совпадает с лексикографическим порядком символов.  Однако, в некоторых европейских языковых стандартах, например, символ «a» \(значение 0x61\) предшествует символу «ä» \(значение 0xE4\) в кодировке, но «ä» предшествует символу «a» лексикографически.  Чтобы выполнить лексикографическое сравнение в таком случае, используйте `strcoll` вместо `strcmp`.  Также можно использовать `strxfrm` на исходных строках, а затем использовать `strcmp` на результирующих строках.  
  
 `strcoll`, `stricoll`, `_strncoll` и `_strnicoll` автоматически обрабатывают строки многобайтовой символов в соответствии с текущей кодовой страницей языкового стандарта, так же ведут себя их аналоги, работающие с расширенными \(Юникод\) символами.  Версии этих функций, работающие с многобайтовыми символами \(MBCS\), однако, сравнивают строки согласно текущей многобайтовой кодовой странице.  
  
 Поскольку функции `coll` сопоставляют строки для лексикографического сравнения, тогда как функции `cmp` просто проверяются на равенство строки, функции `coll` гораздо медленнее, чем соответствующие версии `cmp`.  Таким образом, функции `coll` следует использовать только в том случае, когда есть различие между порядком символов в наборе и лексикографическим порядке символов в текущей кодовой странице и данное различие представляет интерес во время сравнения строк.  
  
## См. также  
 [Языковой стандарт](../c-runtime-library/locale.md)   
 [Управление строками](../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [\_mbsnbcoll, \_mbsnbcoll\_l, \_mbsnbicoll, \_mbsnbicoll\_l](../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [strcmp, wcscmp, \_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)