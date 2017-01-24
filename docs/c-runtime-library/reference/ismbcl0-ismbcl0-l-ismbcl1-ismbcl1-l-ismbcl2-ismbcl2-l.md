---
title: "_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l | Microsoft Docs"
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
  - "_ismbcl2"
  - "_ismbcl1"
  - "_ismbcl0"
  - "_ismbcl2_l"
  - "_ismbcl1_l"
  - "_ismbcl0_l"
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
  - "ismbcl0"
  - "_ismbcl1_l"
  - "_ismbcl0"
  - "ismbcl1"
  - "ismbcl0_l"
  - "_ismbcl2_l"
  - "ismbcl2"
  - "ismbcl1_l"
  - "_ismbcl1"
  - "_ismbcl0_l"
  - "_ismbcl2"
  - "ismbcl2_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbcl0 - функция"
  - "_ismbcl0_l - функция"
  - "_ismbcl1 - функция"
  - "_ismbcl1_l - функция"
  - "_ismbcl2 - функция"
  - "_ismbcl2_l - функция"
  - "ismbcl0 - функция"
  - "ismbcl0_l - функция"
  - "ismbcl1 - функция"
  - "ismbcl1_l - функция"
  - "ismbcl2 - функция"
  - "ismbcl2_l - функция"
ms.assetid: ee15ebd1-462c-4a43-95f3-6735836d626a
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Функции, специфичные для кодовой страницы 932**, использующие текущий языковой стандарт или определенную категорию состояния преобразования LC\_CTYPE.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _ismbcl0(  
   unsigned int c   
);  
int _ismbcl0_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcl1(  
   unsigned int c   
);  
int _ismbcl1_l(  
   unsigned int c ,  
   _locale_t locale  
);  
int _ismbcl2(  
   unsigned int c   
);  
int _ismbcl2_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `c`  
 Символ, который требуется проверить.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Каждая из этих процедур возвращает ненулевое значение, если символ удовлетворяет условию теста, или 0, если не удовлетворяет.  Если `c` \<\= 255 и есть соответствующая процедура `_ismbb` \(например, `_ismbcalnum` соответствует `_ismbbalnum`\), то результат равен возвращаемому значению соответствующей процедуры `_ismbb`.  
  
## Заметки  
 Каждая из этих функций проверяет определенный многобайтовый символ на соответствие заданному условию.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../Topic/setlocale,%20_wsetlocale.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версии с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
|Подпрограмма|Условие теста \(только для кодовой страницы 932\)|  
|------------------|-------------------------------------------------------|  
|`_ismbcl0`|Не Кандзи в формате JIS: 0x8140\=\<`c`\<\=0x889E.|  
|`_ismbcl0_l`|Не Кандзи в формате JIS: 0x8140\=\<`c`\<\=0x889E.|  
|`_ismbcl1`|JIS уровня 1: 0x889F\=\<`c`\<\=0x9872.|  
|`_ismbcl1_l`|JIS уровня 1: 0x889F\=\<`c`\<\=0x9872.|  
|`_ismbcl2`|JIS уровня 2: 0x989F\<\=`c`\<\=0xEAA4.|  
|`_ismbcl2_l`|JIS уровня 2: 0x989F\<\=`c`\<\=0xEAA4.|  
  
 Функции проверяют указанное значение `c` на соответствие условиям теста, описанным выше, но не проверяют то, что `c` \- допустимый многобайтовый символ.  Если младший байт в диапазоне 0x00 – 0x3F, 0x7F, or 0xFD – 0xFF, то эти функции возвращают ненулевое значение, показывающее, что символ удовлетворяет условиям теста.  Используйте [\_ismbbtrail](../../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md), чтобы проверить, определен ли многобайтовый символ.  
  
 **Конец специфичных для кодовой страницы 932 функций**  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_ismbcl0`|\<mbstring.h\>|  
|`_ismbcl0_l`|\<mbstring.h\>|  
|`_ismbcl1`|\<mbstring.h\>|  
|`_ismbcl1_l`|\<mbstring.h\>|  
|`_ismbcl2`|\<mbstring.h\>|  
|`_ismbcl2_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Процедуры \_ismbc](../../c-runtime-library/ismbc-routines.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)