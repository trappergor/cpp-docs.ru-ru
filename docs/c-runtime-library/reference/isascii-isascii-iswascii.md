---
title: "isascii, __isascii, iswascii | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "iswascii"
  - "__isascii"
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
  - "iswascii"
  - "istascii"
  - "__isascii"
  - "_istascii"
  - "isascii"
  - "ctype/isascii"
  - "ctype/__isascii"
  - "corecrt_wctype/iswascii"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__isascii - функция"
  - "_isascii - функция"
  - "isascii - функция"
  - "_istascii - функция"
  - "istascii - функция"
  - "iswascii - функция"
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# isascii, __isascii, iswascii
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, является ли определенный символ символ ASCII.  
  
## Синтаксис  
  
```  
int __isascii(   
   int c   
);  
int iswascii(   
   wint_t c   
);  
#define isascii __isascii  
```  
  
#### Параметры  
 `c`  
 Проверяемое целое число.  
  
## Возвращаемое значение  
 Каждый из этих подпрограмм возвращает ненулевое значение, если `c` — конкретное представление символа в кодировке ASCII.`__isascii` возвращает ненулевое значение, если `c` является символ ASCII \(в диапазоне от 0x00 до 0x7F\).`iswascii` возвращает ненулевое значение, если `c` является представлением Юникода символ ASCII. Каждая из этих подпрограмм возвращает 0, если `c` не удовлетворяет проверяемому условию.  
  
## Заметки  
 Оба `__isascii` и `iswascii` реализуются как макросы \_CTYPE\_DISABLE\_MACROS макрос препроцессора не определен.  
  
 Для обеспечения обратной совместимости `isascii` реализуется как макрос, только если [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) не определено или задано значение 0; в противном случае он не определен.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_istascii`|`__isascii`|`__isascii`|`iswascii`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`isascii`, `__isascii`|C: \< ctype.h \><br /><br /> C\+\+: \< cctype \> или \< ctype.h \>|  
|`iswascii`|C: \< wctype.h \>, \< ctype.h \> или \< wchar.h \><br /><br /> C\+\+: \< cwctype \>, \< cctype \>, \< wctype.h \>, \< ctype.h \> или \< wchar.h \>|  
  
 `isascii`, `__isascii` И `iswascii` функции, определенные Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)