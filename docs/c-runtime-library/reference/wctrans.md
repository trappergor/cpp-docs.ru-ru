---
title: "wctrans | Microsoft Docs"
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
  - "wctrans"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wctrans"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "коды символов, wctrans"
  - "знаки, коды"
  - "знаки, преобразование"
  - "wctrans - функция"
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wctrans
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет сопоставление одного набора кодов символов в другой.  
  
## Синтаксис  
  
```  
wctrans_t wctrans(  
   const char *property   
);  
```  
  
#### Параметры  
 `property`  
 Строка, которая определяет одно из допустимых преобразований.  
  
## Возвращаемое значение  
 Если категория `LC_CTYPE` текущего языкового стандарта не определяет сопоставление, имя которого соответствует строке свойства `property`, функция возвращает ноль.  В противном случае возвращается ненулевое значение, подходящее для использования в качестве второго аргумента следующего вызова [towctrans](../../c-runtime-library/reference/towctrans.md).  
  
## Заметки  
 Эта функция определяет сопоставление одного набора кодов символов в другой.  
  
 Следующие пары вызовов имеют одинаковое поведение для всех языковых стандартов, но можно указать дополнительные сопоставления даже в языковом стандарте «C».  
  
|Функция|Эквивалентно|  
|-------------|------------------|  
|`tolower(`  `c`  `)`|`towctrans(`  `c` `, wctrans("towlower" ) )`|  
|`towupper(`  `c`  `)`|`towctrans(`  `c` `, wctrans( "toupper" ) )`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`wctrans`|\<wctype.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_wctrans.cpp  
// compile with: /EHsc  
// This example determines a mapping from one set of character  
// codes to another.   
  
#include <wchar.h>  
#include <wctype.h>  
#include <stdio.h>  
#include <iostream>  
  
int main()   
{  
    wint_t c = 'a';  
    printf_s("%d\n",c);  
  
    wctrans_t i = wctrans("toupper");  
    printf_s("%d\n",i);  
  
    wctrans_t ii = wctrans("towlower");  
    printf_s("%d\n",ii);  
  
    wchar_t wc = towctrans(c, i);  
    printf_s("%d\n",wc);  
}  
```  
  
  **97**  
**1**  
**0**  
**65**   
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)