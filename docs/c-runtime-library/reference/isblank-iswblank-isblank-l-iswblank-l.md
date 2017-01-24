---
title: "isblank, iswblank, _isblank_l, _iswblank_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "isblank"
  - "_isblank_l"
  - "iswblank"
  - "_iswblank_l"
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
  - "_iswblank_l"
  - "isblank"
  - "_istblank_l"
  - "_istblank"
  - "_isblank_l"
  - "iswblank"
dev_langs: 
  - "C++"
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isblank, iswblank, _isblank_l, _iswblank_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, представляет ли целое число пустой символ.  
  
## Синтаксис  
  
```  
int isblank(  
   int c   
);  
int iswblank(  
   wint_t c   
);  
int _isblank_l(  
   int c,  
   _locale_t locale  
);  
int _iswblank_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `c`  
 Целое число, которое требуется проверить.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Каждая из этих процедур возвращает отличное от нуля, если `c` — конкретное представление пробела или знаков горизонтальной табуляции, или один из наборов символов для языкового стандарта, используемых для разделения ключевые слов в пределах строки текста.  `isblank` возвращает ненулевое значение, если `c` — символ пробела \(0x20\) или символ горизонтальный табуляции, \(0x09\).  Результат условия проверки для функций `isblank` зависит от значения категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 `iswblank` возвращает ненулевое значение, если `c` — расширенный символ, который соответствует стандартному пробелу или символу горизонтальный табуляции.  
  
 Поведение `isblank` и `_isblank_l` является неопределенным, если `c` не является концом файла или не находится в диапазоне с 0 по 0xFF включительно.  При использовании библиотеки CRT отладки и `c` не является одним из этих значений, функции вызывают утверждение.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_istblank`|`isblank`|[\_ismbcblank](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswblank`|  
|`_istblank_l`|`_isblank_l`|[\_ismbcblank\_l](../../c-runtime-library/reference/ismbcgraph-functions.md)|`_iswblank_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`isblank`|\<ctype.h\>|  
|`iswblank`|\<ctype.h\> или \<wchar.h\>|  
|`_isblank_l`|\<ctype.h\>|  
|`_iswblank_l`|\<ctype.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 [System::Char::IsWhiteSpace](https://msdn.microsoft.com/en-us/library/system.char.iswhitespace.aspx)  
  
## См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)