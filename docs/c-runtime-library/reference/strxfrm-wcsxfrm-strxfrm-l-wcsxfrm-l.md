---
title: "strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strxfrm"
  - "_wcsxfrm_l"
  - "_strxfrm_l"
  - "wcsxfrm"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "strxfrm"
  - "_tcsxfrm"
  - "wcsxfrm"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_strxfrm_l - функция"
  - "_tcsxfrm - функция"
  - "_wcsxfrm_l - функция"
  - "сравнение строк [C++], преобразование строк"
  - "строки [C++], сравнение языковых стандартов"
  - "strxfrm - функция"
  - "strxfrm_l - функция"
  - "tcsxfrm - функция"
  - "wcsxfrm - функция"
  - "wcsxfrm_l - функция"
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует строку на основе данных языкового стандарта.  
  
## Синтаксис  
  
```  
size_t strxfrm(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
size_t wcsxfrm(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
size_t _strxfrm_l(  
   char *strDest,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
size_t wcsxfrm_l(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `strDest`  
 Конечная строка.  
  
 `strSource`  
 Исходная строка.  
  
 `count`  
 Наибольшее число символов, которые могут быть размещены в `strDest`*.*  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Возвращает длину преобразованной строки, не считая завершающий символ null.  Если возвращаемое значение больше либо равно `count`, содержимое `strDest` непредсказуемо.  При возникновении ошибки каждая функция устанавливает значение `errno` и возвращает `INT_MAX`.  Для недопустимого символа `errno` получает значение `EILSEQ`.  
  
## Заметки  
 Функция `strxfrm` преобразует строку, на которую указывает `strSource`, в новую упорядоченную форму, которая хранится в `strDest`.  Преобразуется и размещается в результирующей строке не более `count` символов, включая завершающий символ null.  Преобразование осуществляется с помощью параметра категории `LC_COLLATE` языкового стандарта.  Дополнительные сведения по `LC_COLLATE` см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  `strxfrm` использует текущий языковой стандарт для своего поведения, зависящего от языкового стандарта; `_strxfrm_l` идентична предыдущей функции за исключением того, что она использует языковой стандарт, который передается в качестве параметра, вместо текущего языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 После преобразования вызов `strcmp` с двумя преобразованными строками дает результаты, которые идентичны результату вызова `strcoll` применительно к двум исходным строкам.  Как и `strcoll` и `stricoll`, `strxfrm` автоматически обрабатывает многобайтовые строки при необходимости.  
  
 `wcsxfrm` — это двухбайтовая версия `strxfrm`; строковые аргументы для `wcsxfrm` представляют собой двухбайтовые указатели.  Для `wcsxfrm` после преобразования строки вызов `wcscmp` с двумя преобразованными строками дает результаты, которые идентичны результату вызова `wcscoll` применительно к двум исходным строкам.  В остальных случаях поведение `wcsxfrm` и `strxfrm` идентично.  `wcsxfrm` использует текущий языковой стандарт для своего поведения, зависящего от языкового стандарта;. `_wcsxfrm_l` использует языковой стандарт, который передается в качестве параметра, вместо текущего языкового стандарта.  
  
 Эти функции проверяют свои параметры.  Если `strSource` \- пустой указатель или `strDest` \- пустой указатель \(если count не равно нулю\) или если `count` больше `INT_MAX`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают `INT_MAX`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsxfrm`|`strxfrm`|`strxfrm`|`wcsxfrm`|  
|`_tcsxfrm_l`|`_strxfrm_l`|`_strxfrm_l`|`_wcsxfrm_l`|  
  
 В языковом стандарте "C" порядок символов в кодировке \(кодировка ASCII\) совпадает с лексикографическим порядком символов.  Однако в других языковых стандартах порядок символов в кодировке может отличаться от лексикографического порядка символов.  Например, в некоторых европейских языковых стандартах символ 'a' \(значение 0x61\) предшествует символу '&\#x00E4;' \(значение 0xE4\) в кодировке, но 'ä' предшествует символу 'a' лексикографически.  
  
 При использовании языковых стандартов, в которых порядок символов в кодировке и лексикографический порядок различаются, используйте `strxfrm` на исходных строках, а затем `strcmp` на результирующих строках для лексикографического сравнения строк согласно категории `LC_COLLATE` текущего языкового стандарта.  Таким образом, чтобы сравнить две строки лексикографически в приведенном ранее языковом стандарте, используйте `strxfrm` на исходных строках, затем `strcmp` на результирующих строках.  Кроме того, можно использовать `strcoll` вместо `strcmp` на исходных строках.  
  
 `strxfrm` представляет собой оболочку [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) с `LCMAP_SORTKEY`.  
  
 Значение следующего выражения \- это размер массива, необходимого для хранения `strxfrm` преобразования исходной строки:  
  
```  
1 + strxfrm( NULL, string, 0 )  
```  
  
 Только в языковом стандарте "C", `strxfrm` эквивалентно следующему:  
  
```  
strncpy( _string1, _string2, _count );  
return( strlen( _string1 ) );  
```  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strxfrm`|\<string.h\>|  
|`wcsxfrm`|\<string.h\> или \<wchar.h\>|  
|`_strxfrm_l`|\<string.h\>|  
|`_wcsxfrm_l`|\<string.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [strcmp, wcscmp, \_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)