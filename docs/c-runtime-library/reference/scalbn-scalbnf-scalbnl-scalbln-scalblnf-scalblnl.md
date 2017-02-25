---
title: "scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "scalblnl"
  - "scalbnl"
  - "scalbnf"
  - "scalblnf"
  - "scalbn"
  - "scalbln"
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
  - "scalblnf"
  - "scalbnl"
  - "scalblnl"
  - "scalbln"
  - "scalbn"
  - "scalbnf"
dev_langs: 
  - "C++"
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Умножает число с плавающей запятой на целую степень числа FLT\_RADIX.  
  
## Синтаксис  
  
```  
double scalbn(    double x,    int exp  ); float scalbn(    float x,    int exp );  // C++ only long double scalbn(    long double x,    int exp );  // C++ only  float scalbnf(    float x,    int exp );  long double scalbnl(    long double x,    int exp ); double scalbln(    double x,    long exp  ); float scalbln(    float x,    long exp );  // C++ only long double scalbln(    long double x,    long exp );  // C++ only  float scalblnf(    float x,    long exp );  long double scalblnl(    long double x,    long exp );  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей запятой.  
  
 `exp`  
 Целый показатель степени.  
  
## Возвращаемое значение  
 Функции `scalbn` возвращают значение `x` \* `FLT_RADIX`<sup>exp</sup> в случае успешного выполнения.  При переполнении \(в зависимости от знака числа `x`\) функция `scalbn` возвращает \+\/\- `HUGE_VAL`; для `errno` задается значение `ERANGE`.  
  
 Дополнительные сведения о макросе `errno` и возможных возвращаемых значениях ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 `FLT_RADIX` определяется в \<float.h\> как собственное основание числа с плавающей запятой; в двоичных системах имеет значение 2, а функция `scalbn` эквивалентна [ldexp](../../c-runtime-library/reference/ldexp.md).  
  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `scalbn` и `scalbln`, которые принимают и возвращают типы `float` или `long double`.  В программе на языке C функция `scalbn` всегда принимает значение `double` и `int` и возвращает значение `double`, а функция `scalbln` всегда принимает значение `double` и `long` и возвращает значение `double`.  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`scalbn`, `scalbnf`, `scalbnl`, `scalbln`, `scalblnf`, `scalblnl`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_scalbn.c  
// Compile using: cl /W4 crt_scalbn.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 6.4, y;  
   int p = 3;  
  
   y = scalbn( x, p );  
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );  
}  
```  
  
## Вывод  
  
```  
6.4 times FLT_RADIX to the power of 3 is 51.2  
```  
  
## Эквивалент в .NET Framework  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)