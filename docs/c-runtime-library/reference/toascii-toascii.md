---
title: "toascii __toascii | Microsoft Docs"
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
  - "__toascii"
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
  - "__toascii"
  - "toascii"
  - "ctype/toascii"
  - "ctype/__toascii"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "toascii - функция"
  - "преобразование строк, в ASCII-знаки"
  - "__toascii - функция"
  - "Символы ASCII, преобразование"
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# toascii __toascii
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует символы в 7\-разрядный код ASCII, проводимой методом усечения.  
  
## Синтаксис  
  
```  
int __toascii(  
   int c   
);  
#define toascii __toascii  
```  
  
#### Параметры  
 `c`  
 Преобразуемый знак.  
  
## Возвращаемое значение  
 `__toascii` Преобразует значение `c` в 7\-разрядный код ASCII в диапазоне и возвращает результат. Возвращаемое значение не зарезервирован для указания ошибки.  
  
## Заметки  
 `__toascii` Подпрограммы Преобразует заданный символ символ ASCII путем его усечения для младших 7 бит. Другие преобразование не применяется.  
  
 `__toascii` Определяется как макрос \_CTYPE\_DISABLE\_MACROS макрос препроцессора не определен. Для обеспечения обратной совместимости `toascii` определен в качестве макроса только если [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) не определено или задано значение 0; в противном случае он не определен.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`toascii`, `__toascii`|C: \< ctype.h \><br /><br /> C\+\+: \< cctype \> или \< ctype.h \>|  
  
 `toascii` Макрос является расширением POSIX и `__toascii` является реализацией Майкрософт расширение POSIX. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)   
 [Функции to](../../c-runtime-library/to-functions.md)