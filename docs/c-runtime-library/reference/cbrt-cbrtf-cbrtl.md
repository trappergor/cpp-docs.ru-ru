---
title: "cbrt, cbrtf, cbrtl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "cbrt"
  - "cbrtf"
  - "cbrtl"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "cbrtl"
  - "cbrt"
  - "cbrtf"
dev_langs: 
  - "C++"
ms.assetid: ab51d916-3db2-4beb-b46a-28b4062cd33f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# cbrt, cbrtf, cbrtl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет кубический корень.  
  
## Синтаксис  
  
```  
double cbrt(    double x  ); float cbrt(    float x  );  // C++ only long double cbrt(    long double x );  // C++ only float cbrtf(    float x  ); long double cbrtl(    long double x );  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей запятой  
  
## Возвращаемое значение  
 Функции `cbrt` возвращают кубический корень `x`.  
  
|Ввод|Исключение SEH|Исключение `_matherr`|  
|----------|--------------------|---------------------------|  
|± ∞, QNAN, IND|Нет|Нет|  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `cbrt`, которые принимают типы `float` или `long double`.  В программе на языке C `cbrt` всегда принимает и возвращает `double`.  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`cbrt`, `cbrtf`, `cbrtl`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```c  
// crt_cbrt.c  
// Compile using: cl /W4 crt_cbrt.c  
// This program calculates a cube root.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double question = -64.64;  
   double answer;  
  
   answer = cbrt(question);  
   printf("The cube root of %.2f is %.6f\n", question, answer);  
}  
```  
  
  **The cube root of \-64.64 is \-4.013289**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../Topic/log,%20logf,%20log10,%20log10f.md)   
 [pow, powf, powl](../Topic/pow,%20powf,%20powl.md)