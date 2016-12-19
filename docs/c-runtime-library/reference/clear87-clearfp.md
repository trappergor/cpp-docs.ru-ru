---
title: "_clear87, _clearfp | Microsoft Docs"
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
  - "_clearfp"
  - "_clear87"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "clearfp"
  - "_clearfp"
  - "_clear87"
  - "clear87"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_clear87 - функция"
  - "_clearfp - функция"
  - "clear87 - функция"
  - "clearfp - функция"
  - "очистка слова, обозначающего статус плавающей запятой"
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _clear87, _clearfp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает и очищает слово состояния модуля операций с плавающей запятой.  
  
## Синтаксис  
  
```  
unsigned int _clear87( void );  
unsigned int _clearfp( void );  
```  
  
## Возвращаемое значение  
 Биты в возвращаемом значении указывают состояние модуля операций с плавающей запятой до вызова функций `_clear87` и `_clearfp`.  Полные определения битов, возвращаемых функцией `_clear87`, см. в файле Float.h.  Многие математические библиотечные функции изменяют слово состояния 8087\/80287 с непредсказуемыми результатами.  Чем меньше операций с плавающей запятой выполняется между известными значениями слова состояния модуля операций с плавающей запятой, тем надежнее возвращаемые из функций `_clear87` и `_status87` значения.  
  
## Заметки  
 Функция `_clear87` очищает флаги исключения в слове состояния операций с плавающей запятой, устанавливает бит занятости в 0 и возвращает слово состояния.  Слово состояния — это сочетание слова состояния 8087\/80287 и других условий, обнаруженных обработчиком исключений 8087\/80287, таких как переполнение стека или потеря точности.  
  
 `_clearfp` — независимая от платформы, переносимая версия функции `_clear87`.  Она идентична функции `_clear87` на платформах Intel \(x86\) и также поддерживается платформами x64 и ARM.  Чтобы код, выполняющий операции с плавающей запятой, был переносимым на архитектуры x64 и ARM, используйте функцию `_clearfp`.  Если код предназначен только для платформ x86, можно использовать функцию `_clear87` или `_clearfp`.  
  
 Эти функции игнорируются в случае компилирования с параметром [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md) или `/clr:pure`, поскольку среда CLR поддерживает только точность чисел с плавающей запятой по умолчанию.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_clear87`|\<float.h\>|  
|`_clearfp`|\<float.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_clear87.c  
// compile with: /Od  
  
// This program creates various floating-point   
// problems, then uses _clear87 to report on these problems.  
// Compile this program with Optimizations disabled (/Od).   
// Otherwise the optimizer will remove the code associated with   
// the unused floating-point values.  
//  
  
#include <stdio.h>  
#include <float.h>  
  
int main( void )  
{  
   double a = 1e-40, b;  
   float x, y;  
  
   printf( "Status: %.4x - clear\n", _clear87()  );  
  
   // Store into y is inexact and underflows:  
   y = a;  
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );  
  
   // y is denormal:   
   b = y;  
   printf( "Status: %.4x - denormal\n", _clear87() );  
}  
```  
  
  **Состояние: 0000 — очистить**  
**Состояние: 0003 — потеря значимости, неточный**  
**Состояние: 80 000 — ненормализованный**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)