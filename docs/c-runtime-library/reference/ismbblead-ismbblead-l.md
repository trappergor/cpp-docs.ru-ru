---
title: "_ismbblead, _ismbblead_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbblead_l"
  - "_ismbblead"
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
  - "ismbblead_l"
  - "istlead"
  - "_ismbblead"
  - "_ismbblead_l"
  - "ismbblead"
  - "_istlead"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbblead_l - функция"
  - "ismbblead - функция"
  - "_ismbblead - функция"
  - "istlead - функция"
  - "ismbblead_l - функция"
  - "_istlead - функция"
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _ismbblead, _ismbblead_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет символ, чтобы определить, является ли он старшим байтом многобайтового символа.  
  
## Синтаксис  
  
```  
int _ismbblead(  
   unsigned int c   
);  
int _ismbblead_l(  
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
 Возвращает ненулевое значение, если целочисленное значение `c` является первым байтом многобайтового символа.  
  
## Заметки  
 Многобайтовые символы состоят из старшего байта, за которым следует конечный байт. Старшие байты относятся к определенному диапазону данной кодировки. Например, только в кодовой странице 932 старшие байты относятся к диапазону от 0x81 до 0x9F и от 0xE0 до 0xFC.  
  
 Функция `_ismbblead` использует текущий языковой стандарт для поведения, зависящего от языкового стандарта. Функция `_ismbblead_l` идентична за исключением того, что использует переданный языковой стандарт. Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_istlead`|Всегда возвращает значение false|`_ismbblead`|Всегда возвращает значение false|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_ismbblead`|\<mbctype.h\> или \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
|`_ismbblead_l`|\<mbctype.h\> или \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
  
 \* Для констант манифестов, используемых в условиях проверки.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)   
 [Процедуры \_ismbb](../../c-runtime-library/ismbb-routines.md)