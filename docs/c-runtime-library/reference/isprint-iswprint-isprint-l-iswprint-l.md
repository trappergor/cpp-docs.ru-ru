---
title: "isprint, iswprint, _isprint_l, _iswprint_l | Microsoft Docs"
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
  - "iswprint"
  - "isprint"
  - "_isprint_l"
  - "_iswprint_l"
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
  - "iswprint"
  - "_istprint"
  - "isprint"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_isprint_l - функция"
  - "_istprint - функция"
  - "_iswprint_l - функция"
  - "isprint - функция"
  - "isprint_l - функция"
  - "istprint - функция"
  - "iswprint - функция"
  - "iswprint_l - функция"
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isprint, iswprint, _isprint_l, _iswprint_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, представляет ли целое число печатный символ.  
  
## Синтаксис  
  
```  
int isprint(  
   int c   
);  
int iswprint(  
   wint_t c   
);  
int _isprint_l(  
   int c,  
   _locale_t locale  
);  
int _iswprint_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `c`  
 Целое число, которое требуется проверить.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Каждая из этих процедур возвращает отличное от нуля значение, если `c` — конкретное представление печатного символа.  `isprint` возвращает ненулевое значение, если `c` — печатный символ, в том числе пробел \(0x20 — 0x7E\).  `iswprint` возвращает ненулевое значение, если `c` — расширенный печатный символ, в том числе расширенный пробел.  Каждая из этих процедур возвращает 0, если `c` не удовлетворяет условию теста.  
  
 Результат условия проверки для этих функций зависит от значения категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Поведение `isprint` и `_isprint_l` является неопределенным, если `c` не является концом файла или не находится в диапазоне от 0 до 0xFF включительно.  При использовании библиотеки CRT отладки и `c` не является одним из этих значений, функции вызывают утверждение.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_unicode определена|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|**\_** `istprint`|`isprint`|[\_ismbcprint](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswprint`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`isprint`|\<ctype.h\>|  
|`iswprint`|\<ctype.h\> или \<wchar.h\>|  
|`_isprint_l`|\<ctype.h\>|  
|`_iswprint_l`|\<ctype.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)