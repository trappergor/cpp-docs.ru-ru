---
title: "_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l | Microsoft Docs"
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
  - "_ismbckata"
  - "_ismbchira_l"
  - "_ismbchira"
  - "_ismbckata_l"
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
  - "ismbckata_l"
  - "_ismbckata_l"
  - "ismbckata"
  - "ismbchira"
  - "_ismbckata"
  - "ismbchira_l"
  - "_ismbchira_l"
  - "_ismbchira"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbchira - функция"
  - "_ismbchira_l - функция"
  - "_ismbckata - функция"
  - "_ismbckata_l - функция"
  - "Хирагана"
  - "ismbchira - функция"
  - "ismbchira_l - функция"
  - "ismbckata - функция"
  - "ismbdkata_l - функция"
  - "Катакана"
ms.assetid: 2db388a2-be31-489b-81c8-f6bf3f0582d3
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Функции, специфичные для кодовой страницы 932**  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _ismbchira(  
   unsigned int c   
);  
int _ismbchira_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbckata(  
   unsigned int c   
);  
int _ismbckata_l(  
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
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что для поведения, зависящего от языкового стандарта, они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
|Подпрограмма|Условие теста \(только для кодовой страницы 932\)|  
|------------------|-------------------------------------------------------|  
|`_ismbchira`|Двухбайтовая Хирагана: 0x829F\=\<`c`\<\=0x82F1.|  
|`_ismbchira_l`|Двухбайтовая Хирагана: 0x829F\=\<`c`\<\=0x82F1.|  
|`_ismbckata`|Двухбайтовая катакана: 0x8340\=\<`c`\<\=0x8396.|  
|`_ismbckata_l`|Двухбайтовая катакана: 0x8340\=\<`c`\<\=0x8396.|  
  
 **Конец специфичных для кодовой страницы 932 функций**  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_ismbchira`|\<mbstring.h\>|  
|`_ismbchira_l`|\<mbstring.h\>|  
|`_ismbckata`|\<mbstring.h\>|  
|`_ismbckata_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Процедуры \_ismbc](../../c-runtime-library/ismbc-routines.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)