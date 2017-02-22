---
title: "wctype | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wctype"
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
apitype: "DLLExport"
f1_keywords: 
  - "wctype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wctype - функция"
  - "расширенные символы"
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# wctype
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет правило классификации кодов расширенных символов.  
  
## Синтаксис  
  
```  
wctype_t wctype(  
   const char * property   
);  
```  
  
#### Параметры  
 `property`  
 Строка свойства.  
  
## Возвращаемое значение  
 Если категория `LC_CTYPE` текущего языкового стандарта не определяет правило классификации, имя которого соответствует строке свойства `property`, функция возвращает ноль.  В противном случае возвращается ненулевое значение, подходящее для использования в качестве второго аргумента следующего вызова [towctrans](../../c-runtime-library/reference/towctrans.md).  
  
## Заметки  
 Функция определяет правило классификации кодов расширенных символов.  Следующие пары вызовов имеют аналогичное поведение во всех языковых стандартах \(но реализация позволяет определить дополнительные правила классификации даже в языковом стандарте "C"\).  
  
|Функция|Эквивалентно|  
|-------------|------------------|  
|`iswalnum(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alnum" ) )`|  
|`iswalpha(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alpha" ) )`|  
|`iswcntrl(`  `c`  `)`|`iswctype(`  `c` `, wctype( "cntrl" ) )`|  
|`iswdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "digit" ) )`|  
|`iswgraph(`  `c`  `)`|`iswctype(`  `c` `, wctype( "graph" ) )`|  
|`iswlower(`  `c`  `)`|`iswctype(`  `c` `, wctype( "lower" ) )`|  
|`iswprint(`  `c`  `)`|`iswctype(`  `c` `, wctype( "print" ) )`|  
|`iswpunct(`  `c`  `)`|`iswctype(`  `c` `, wctype( "punct" ) )`|  
|`iswspace(`  `c`  `)`|`iswctype(`  `c` `, wctype( "space" ) )`|  
|`iswupper(`  `c`  `)`|`iswctype(`  `c` `, wctype( "upper" ) )`|  
|`iswxdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "xdigit" ) )`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`wctype`|\<wctype.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)