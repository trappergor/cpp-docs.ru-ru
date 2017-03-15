---
title: "_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbicoll_l"
  - "_mbsnbcoll_l"
  - "_mbsnbcoll"
  - "_mbsnbicoll"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbsnbicoll"
  - "mbsnbcoll"
  - "mbsnbicoll_l"
  - "_mbsnbcoll"
  - "_mbsnbicoll"
  - "_ftcsnicoll"
  - "_ftcsncoll"
  - "mbsnbcoll_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbcoll - функция"
  - "_mbsnbcoll_l - функция"
  - "_mbsnbicoll - функция"
  - "_mbsnbicoll_l - функция"
  - "_tcsncoll - функция"
  - "_tcsnicoll - функция"
  - "mbsnbcoll - функция"
  - "mbsnbcoll_l - функция"
  - "mbsnbicoll - функция"
  - "mbsnbicoll_l - функция"
  - "tcsncoll - функция"
  - "tcsnicoll - функция"
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сравнивает `n` байтов двух строк многобайтовой кодировки с помощью сведений многобайтовой кодовой страницы.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _mbsnbcoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbcoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnbicoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `string1, string2`  
 Строка для сравнения.  
  
 `count`  
 Число байтов для сравнения.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Возвращаемое значение указывает отношение подстрок `string1` и `string2`.  
  
|Возвращаемое значение|Описание|  
|---------------------------|--------------|  
|\< 0|подстрока `string1` меньше, чем подстрока `string2`.|  
|0|Подстрока `string1` идентична подстроке `string2`.|  
|\> 0|Подстрока `string1` больше, чем подстрока `string2`.|  
  
 Если `string1` или `string2` имеет значение `NULL` или `count` превосходит `INT_MAX`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `_NLSCMPERROR` и устанавливают для `errno` значение `EINVAL`.  Для использования `_NLSCMPERROR` включите либо String.h, либо Mbstring.h.  
  
## Заметки  
 Каждая из этих функций сравнивает, по крайней мере, первые `count` байтов в `string1` и `string2` и возвращает значение, указывающее отношение между результирующее подстроками `string1` и `string2`.  Если конечный байт в подстроке `string1` или `string2` является ведущим байтом, он не учитывается при сравнении; эти функции сравнивают только полные символы в подстроках.  `_mbsnbicoll` — нечувствительная к регистру версия `_mbsnbcoll`.  Подобно `_mbsnbcmp` и `_mbsnbicmp`, `_mbsnbcoll` и `_mbsnbicoll` сравнивают две строки многобайтовой кодировки в соответствии с лексикографическим порядком, определенным текущей многобайтовой [кодовой страницей](../../c-runtime-library/code-pages.md).  
  
 Для некоторых кодовых страниц и соответствующих наборов символов порядок символов в наборе может отличаться от лексикографического порядка символов.  Языковой стандарт "C" не входит в их число: порядок символов в кодировке ASCII совпадает с лексикографическим порядком символов.  Однако, в некоторых европейских языковых стандартах, например, символ «a» \(значение 0x61\) предшествует символу «ä» \(значение 0xE4\) в кодировке, но «ä» предшествует символу «a» лексикографически.  Чтобы выполнить лексикографическое сравнение строк байтов в таком случае, используйте `_mbsnbcoll` вместо `_mbsnbcmp`; для проверки только на равенство строк используйте `_mbsnbcmp`.  
  
 Поскольку функции `coll` сопоставляют строки для лексикографического сравнения, тогда как функции `cmp` просто проверяются на равенство строки, функции `coll` гораздо медленнее, чем соответствующие версии `cmp`.  Таким образом, функции `coll` следует использовать только в том случае, когда есть различие между порядком символов в наборе и лексикографическим порядке символов в текущей кодовой странице и данное различие представляет интерес во время сравнения.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsncoll`|[\_strncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll`|[\_wcsncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsncoll_l`|[\_strncoll, \_wcsncoll, \_mbsncoll, \_strncoll\_l, \_wcsncoll\_l, \_mbsncoll\_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll_l`|[\_wcsncoll\_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsnicoll`|[\_strnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll`|[\_wcsnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
|`_tcsnicoll_l`|[\_strnicoll\_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll_l`|[\_wcsnicoll\_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_mbsnbcoll`|\<mbstring.h\>|  
|`_mbsnbcoll_l`|\<mbstring.h\>|  
|`_mbsnbicoll`|\<mbstring.h\>|  
|`_mbsnbicoll_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_mbsnbicmp, \_mbsnbicmp\_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)