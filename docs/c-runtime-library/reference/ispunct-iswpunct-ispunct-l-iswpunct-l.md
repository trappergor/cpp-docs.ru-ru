---
title: "ispunct, iswpunct, _ispunct_l, _iswpunct_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ispunct"
  - "_iswpunct_l"
  - "iswpunct"
  - "_ispunct_l"
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
  - "iswpunct"
  - "_istpunct"
  - "ispunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ispunct_l - функция"
  - "_istpunct - функция"
  - "_iswpunct_l - функция"
  - "ispunct - функция"
  - "ispunct_l - функция"
  - "istpunct - функция"
  - "iswpunct - функция"
  - "iswpunct_l - функция"
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# ispunct, iswpunct, _ispunct_l, _iswpunct_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, представляет ли целое число символ пунктуации.  
  
## Синтаксис  
  
```  
int ispunct(  
   int c   
);  
int iswpunct(  
   wint_t c   
);  
int _ispunct_l(  
   int c,  
   _locale_t locale  
);  
int _iswpunct_l(  
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
 Каждая из этих процедур возвращает отличное от нуля значение, если `c` — конкретное представление символа пунктуации.  `ispunct` возвращает ненулевое значение для любого печатного символа, который не является пробельным символом или символом, для которого `isalnum` отлично от нуля.  `iswpunct` возвращает ненулевое значение для любого печатного расширенного символа, который не является ни пробельным расширенным символом, ни расширенным символом, для которого `iswalnum` отлично от нуля.  Каждая из этих процедур возвращает 0, если `c` не удовлетворяет условию теста.  
  
 Результат условия проверки для функции `ispunct` зависит от значения категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Поведение `ispunct` и `_ispunct_l` является неопределенным, если `c` не является концом файла или не находится в диапазоне от 0 до 0xFF включительно.  При использовании библиотеки CRT отладки и `c` не является одним из этих значений, функции вызывают утверждение.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|**\_** `istpunct`|`ispunct`|[\_ismbcpunct](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswpunct`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`ispunct`|\<ctype.h\>|  
|`iswpunct`|\<ctype.h\> или \<wchar.h\>|  
|`_ispunct_l`|\<ctype.h\>|  
|`_iswpunct_l`|\<ctype.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)