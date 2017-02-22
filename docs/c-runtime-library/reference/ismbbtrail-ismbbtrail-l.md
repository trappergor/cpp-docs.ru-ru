---
title: "_ismbbtrail, _ismbbtrail_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbbtrail"
  - "_ismbbtrail_l"
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
  - "_ismbbtrail"
  - "ismbbtrail"
  - "_ismbbtrail_l"
  - "ismbbtrail_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ismbbtrail_l - функция"
  - "_ismbbtrail - функция"
  - "_ismbbtrail_l - функция"
  - "ismbbtrail - функция"
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _ismbbtrail, _ismbbtrail_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, является ли байт конечным байтом многобайтового символа.  
  
## Синтаксис  
  
```  
int _ismbbtrail(  
   unsigned int c   
);  
int _ismbbtrail_l(  
   unsigned int c,  
   _locale_t locale   
);  
```  
  
#### Параметры  
 `c`  
 Целое число, которое требуется проверить.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 `_ismbbtrail` возвращает ненулевое значение, если целочисленное значение `c` является вторым байтом многобайтового символа. Например, только для кодовой страницы 932, допустимые диапазоны: 0x40–0x7E и 0x80–0xFC.  
  
## Заметки  
 Функция `_ismbbtrail` использует текущий языковой стандарт для поведения, зависящего от языкового стандарта. Функция `_ismbbtrail_l` идентична за исключением того, что использует переданный языковой стандарт. Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_ismbbtrail`|\<mbctype.h\> или \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
|`_ismbbtrail_l`|\<mbctype.h\> или \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
  
 \* Для констант манифестов, используемых в условиях проверки.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)   
 [Процедуры \_ismbb](../../c-runtime-library/ismbb-routines.md)