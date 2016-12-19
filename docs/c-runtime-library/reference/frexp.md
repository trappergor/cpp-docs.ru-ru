---
title: "frexp | Microsoft Docs"
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
  - "frexp"
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
  - "frexp"
  - "_frexpl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_frexpl - функция"
  - "показатель степени, числа с плавающей запятой"
  - "функции с плавающей запятой, мантисса и степень"
  - "frexp - функция"
  - "frexpl - функция"
  - "мантисса, переменные с плавающей запятой"
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# frexp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает мантиссу и экспоненту числа с плавающей запятой.  
  
## Синтаксис  
  
```  
double frexp(  
   double x,  
   int *expptr   
);  
float frexp(  
   float x,  
   int * expptr  
);  // C++ only  
long double frexp(  
   long double x,  
   int * expptr  
);  // C++ only  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей запятой.  
  
 `expptr`  
 Указатель на сохраненный целочисленный показатель степени.  
  
## Возвращаемое значение  
 `frexp` возвращает мантиссу.  Если `x` равно 0, функция возвращает 0 как для мантиссы, так и для экспоненты.  Если параметр `expptr` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция устанавливает `errno` в значение `EINVAL` и возвращает 0.  
  
## Заметки  
 Функция `frexp` разделяет значение с плавающей запятой \(`x`\) на мантиссу \(`m`\) и экспоненту \(`n`\), такие, чтобы абсолютное значение `m` было больше или равно 0.5 и меньше 1.0 и `x` \= `m`\*2<sup>n</sup>.  Целочисленный показатель степени `n` хранится в расположении, указанном `expptr`.  
  
 C\+\+ позволяет перегрузку, поэтому можно вызвать перегрузки `frexp`.  В программе на языке C `frexp` всегда принимает целое число и значение double и возвращает значение double.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`frexp`|\<math.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_frexp.c  
// This program calculates frexp( 16.4, &n )  
// then displays y and n.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y;  
   int n;  
  
   x = 16.4;  
   y = frexp( x, &n );  
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );  
}  
```  
  
  **frexp\( 16.400000, &n \) \= 0.512500, n \= 5**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)