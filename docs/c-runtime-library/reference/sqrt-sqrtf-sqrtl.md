---
title: "sqrt, sqrtf, sqrtl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "sqrtl"
  - "sqrtf"
  - "sqrt"
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
  - "sqrt"
  - "sqrtf"
  - "_sqrtl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_sqrtl - функция"
  - "вычисление квадратных корней"
  - "sqrt - функция"
  - "sqrtf - функция"
  - "sqrtl - функция"
  - "квадратные корни, вычисление"
ms.assetid: 2ba9467b-f172-41dc-8f10-b86f68fa813c
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# sqrt, sqrtf, sqrtl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет квадратный корень.  
  
## Синтаксис  
  
```  
double sqrt(    double x  ); float sqrt(    float x  );  // C++ only long double sqrt(    long double x );  // C++ only float sqrtf(    float x  ); long double sqrtl(    long double x  );  
```  
  
#### Параметры  
 `x`  
 Неотрицательные значения с плавающей запятой  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `sqrt`, которые принимают типы `float` или `long double`.  В программе на языке C `sqrt` всегда принимает и возвращает `double`.  
  
## Возвращаемое значение  
 Функции `sqrt` возвращают квадратный корень `x`.  По умолчанию, если `x` является отрицательным числом, функция `sqrt` возвращает неопределенное значение NaN.  
  
|Ввод|Исключение SEH|Исключение `_matherr`|  
|----------|--------------------|---------------------------|  
|± QNAN,IND|Нет|\_DOMAIN|  
|\- ∞|Нет|\_DOMAIN|  
|x \< 0|Нет|\_DOMAIN|  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`sqrt`, `sqrtf`, `sqrtl`|\<math.h\>|\<cmath\>|  
  
 Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_sqrt.c  
// This program calculates a square root.  
  
#include <math.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   double question = 45.35, answer;  
   answer = sqrt( question );  
   if( question < 0 )  
      printf( "Error: sqrt returns %f\n", answer );  
   else  
      printf( "The square root of %.2f is %.2f\n", question, answer );  
}  
```  
  
  **The square root of 45.35 is 6.73**   
## Эквивалент в .NET Framework  
 [System::Math::Sqrt](https://msdn.microsoft.com/en-us/library/system.math.sqrt.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../Topic/log,%20logf,%20log10,%20log10f.md)   
 [pow, powf, powl](../Topic/pow,%20powf,%20powl.md)   
 [\_CIsqrt](../../c-runtime-library/cisqrt.md)