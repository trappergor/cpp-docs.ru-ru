---
title: "iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l | Microsoft Docs"
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
  - "_iswcsym_l"
  - "__iswcsym"
  - "__iscsym"
  - "_iswcsymf_l"
  - "_iscsym_l"
  - "__iswcsymf"
  - "__iscsymf"
  - "_iscsymf_l"
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
  - "_iswcsym_l"
  - "_iswcsymf_l"
  - "iscsymf"
  - "iswcsymf"
  - "__iswcsym"
  - "__iswcsymf"
  - "iscsym"
  - "iswcsym"
  - "__iscsym"
  - "_iscsym_l"
  - "_iscsymf_l"
  - "__iscsymf"
  - "ctype/iscsym"
  - "ctype/iscsymf"
  - "ctype/__iscsym"
  - "ctype/__iscsymf"
  - "ctype/__iscsym_l"
  - "ctype/__iscsymf_l"
  - "ctype/__iswcsym"
  - "ctype/__iswcsymf"
  - "ctype/__iswcsym_l"
  - "ctype/__iswcsymf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "iscsymf_l - функция"
  - "iswsym_l - функция"
  - "_iswcsym_l - функция"
  - "iscsym_l - функция"
  - "_iscsymf_l - функция"
  - "_iswcsymf_l - функция"
  - "_iscsym_l - функция"
  - "__iscsym - функция"
  - "__iswcsymf - функция"
  - "iswsymf_l - функция"
  - "__iscsymf - функция"
  - "__iswcsym - функция"
  - "iscsym - функция"
  - "iscsymf - функция"
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, если целое число представляет символ, который может использоваться в идентификаторе.  
  
## Синтаксис  
  
```  
int __iscsym(   
   int c   
);  
int __iswcsym(   
   wint_t c   
);  
int __iscsymf(   
   int c   
);  
int __iswcsymf(   
   wint_t c   
);  
int _iscsym_l(   
   int c,  
   _locale_t locale  
);  
int _iswcsym_l(   
   wint_t c,  
   _locale_t locale  
);  
int _iscsymf_l(   
   int c,  
   _locale_t locale  
);  
int _iswcsymf_l(   
   wint_t c,  
   _locale_t locale  
);  
#define iscsym __iscsym  
#define iscsymf __iscsymf  
```  
  
#### Параметры  
 `c`  
 Проверяемое целое число.`c` должно быть в диапазоне от 0 до 255 для узких символов версии функции.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Оба `__iscsym` и `__iswcsym` возвращает ненулевое значение, если `c` буквы, символа подчеркивания или цифра. Оба `__iscsymf` и `__iswcsymf` возвращает ненулевое значение, если `c` буквы или символа подчеркивания. Каждая из этих подпрограмм возвращает 0, если `c` не удовлетворяет проверяемому условию. Версии этих функций с суффиксом `_l` идентичны, за исключением того, что для поведения, зависящего от языкового стандарта, они используют переданный параметр языкового стандарта вместо текущего языкового стандарта. Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
## Заметки  
 Эти подпрограммы определены как макросы \_CTYPE\_DISABLE\_MACROS макрос препроцессора не определен. При использовании версий макроса этих процедур, аргументы можно вычислить несколько раз. Будьте внимательны при использовании выражения с побочными эффектами в списке аргументов.  
  
 Для обеспечения обратной совместимости `iscsym` и `iscsymf` определены как макросы только если [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) не определено или задано значение 0; в противном случае они не определены.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l`, `_iswcsymf_l`|C: \< ctype.h \><br /><br /> C\+\+: \< cctype \> или \< ctype.h \>|  
  
 `iscsym`, `iscsymf`, `__iscsym`, `__iswcsym`, `__iscsymf`, `__iswcsymf`, `_iscsym_l`, `_iswcsym_l`, `_iscsymf_l`, И `_iswcsymf_l` подпрограммы, определенные Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)