---
title: "_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l | Microsoft Docs"
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
  - "_ismbclegal_l"
  - "_ismbclegal"
  - "_ismbcsymbol"
  - "_ismbcsymbol_l"
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
  - "ismbcsymbol_l"
  - "_ismbcsymbol_l"
  - "_ismbcsymbol"
  - "_ismbclegal_l"
  - "_ismbclegal"
  - "ismbclegal_l"
  - "ismbcsymbol"
  - "ismbclegal"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbclegal - функция"
  - "_ismbclegal_l - функция"
  - "_ismbcsymbol - функция"
  - "_ismbcsymbol_l - функция"
  - "_istlegal - функция"
  - "_istlegal_l - функция"
  - "ismbclegal - функция"
  - "ismbclegal_l - функция"
  - "ismbcsymbol - функция"
  - "ismbcsymbol_l - функция"
  - "istlegal - функция"
  - "istlegal_l - функция"
ms.assetid: 31bf1ea5-b56f-4e28-b21e-b49a2cf93ffc
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли допустимым многобайтовый символ.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _ismbclegal(  
   unsigned int c   
);  
int _ismbclegal_l(  
   unsigned int c,   
   _locale_t locale  
);  
int _ismbcsymbol(  
   unsigned int c   
);  
int _ismbcsymbol_l(  
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
 Каждая из этих процедур возвращает ненулевое значение, если символ удовлетворяет условию теста, или 0, если не удовлетворяет.  Если `c`\<\= 255 и есть соответствующая процедура `_ismbb` \(например, `_ismbcalnum` соответствует `_ismbbalnum`\), то результат равен возвращаемому значению соответствующей процедуры `_ismbb`.  
  
## Заметки  
 Каждая из этих функций проверяет определенный многобайтовый символ на соответствие заданному условию.  
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что для поведения, зависящего от языкового стандарта, они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
|Подпрограмма|Условие теста|Пример кодовой страницы 932|  
|------------------|-------------------|---------------------------------|  
|`_ismbclegal`|Допустимый многобайтовый символ|Возвращает отличный от нуля результат только если первый байт `c` содержится в диапазоне 0x81 — 0x9F или 0xE0 — 0xFC, а второй байт — в диапазон 0x40 — 0x7E или 0x80 — FC.|  
|`_ismbcsymbol`|Многобайтовый символ|Возвращает отличный от нуля результат только если 0x8141\=\<`c`\<\=0x81AC.|  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_istlegal`|Всегда возвращает значение "false"|`_ismbclegal`|Всегда возвращает значение false.|  
|`_istlegal_l`|Всегда возвращает значение "false"|`_ismbclegal_l`|Всегда возвращает значение false.|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_ismbclegal,_ismbclegal_l`|\<mbstring.h\>|  
|`_ismbcsymbol,_ismbcsymbol_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Процедуры \_ismbc](../../c-runtime-library/ismbc-routines.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)   
 [Процедуры \_ismbb](../../c-runtime-library/ismbb-routines.md)