---
title: "atan, atanf, atanl, atan2, atan2f, atan2l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "atan2f"
  - "atan2l"
  - "atan2"
  - "atanf"
  - "atan"
  - "atanl"
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
  - "atan"
  - "atan2l"
  - "atan2"
  - "atanl"
  - "atanf"
  - "atan2f"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "arctangent - функция"
  - "atan - функция"
  - "atan2 - функция"
  - "atan2f - функция"
  - "atan2l - функция"
  - "atanf - функция"
  - "atanl - функция"
  - "тригонометрические функции"
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# atan, atanf, atanl, atan2, atan2f, atan2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет арктангенс `x` \(`atan`, `atanf` и `atanl`\) или арктангенс `y`\/`x` \(`atan2`, `atan2f` и `atan2l`\).  
  
## Синтаксис  
  
```  
double atan(   
   double x   
);  
float atan(  
   float x   
);  // C++ only  
long double atan(  
   long double x  
);  // C++ only  
double atan2(   
   double y,   
   double x   
);  
float atan2(  
   float y,  
   float x  
);  // C++ only  
long double atan2(  
   long double y,  
   long double x  
);  // C++ only  
float atanf(   
   float x   
);  
long double atanl(  
   long double x  
);  
float atan2f(  
   float y,  
   float x  
);  
long double atan2l(  
   long double y,  
   long double x  
);  
```  
  
#### Параметры  
 `x`, `y`  
 Любые числа.  
  
## Возвращаемое значение  
 `atan` возвращает арктангенс от `x` диапазоне от \-π\/2 до π\/2 радиан.  `atan2` возвращает арктангенс от `y/x` диапазоне от –π до π радиан.  Если `x` равен 0, то `atan` возвращает 0.  Если оба параметра `atan2` равны 0, функция возвращает 0.  Все результаты в радианах.  
  
 `atan2` использует знаки обоих параметров, чтобы определить квадрант возвращаемого значения.  
  
|Ввод|Исключение SEH|Исключение Matherr|  
|----------|--------------------|------------------------|  
|± `QNAN`,`IND`|Нет|`_DOMAIN`|  
  
## Заметки  
 Функция `atan` вычисляет арктангенс \(обратную функцию тангенса\) от `x`.  `atan2` вычисляет арктангенс от `y`\/`x` \(если `x` равно 0, то `atan2` возвращает π\/2, если `y` положительно, π\/2, если `y` отрицательно или равно 0, если `y` равно 0\).  
  
 `atan` имеет реализацию, которая использует набор инструкций SSE2.  Дополнительные сведения и ограничения по использованию реализации с SSE2 см. в разделе [\_set\_SSE2\_enable](../Topic/_set_SSE2_enable.md).  
  
 Поскольку C\+\+ допускает перегрузки, можно вызывать перегрузки `atan` и `atan2`.  В программе на языке C `atan` и `atan2` всегда принимают и возвращают значения типа double.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`atan`, `atan2`, `atanf`, `atan2f`, `atanl`, `atan2l`|\<math.h\>|  
  
## Пример  
  
```  
// crt_atan.c  
// arguments: 5 0.5  
#include <math.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( int ac, char* av[] )   
{  
   double x, y, theta;  
   if( ac != 3 ){  
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );  
      return 1;  
   }  
   x = atof( av[1] );  
   theta = atan( x );  
   printf( "Arctangent of %f: %f\n", x, theta );  
   y = atof( av[2] );  
   theta = atan2( y, x );  
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );   
   return 0;  
}  
```  
  
  **Arctangent of 5.000000: 1.373401**  
**Arctangent of 0.500000 \/ 5.000000: 0.099669**   
## Эквивалент в .NET Framework  
  
-   [System::Math::Atan](https://msdn.microsoft.com/en-us/library/system.math.atan.aspx)  
  
-   [System::Math::Atan2](https://msdn.microsoft.com/en-us/library/system.math.atan2.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [\_CIatan](../Topic/_CIatan.md)   
 [\_CIatan2](../../c-runtime-library/ciatan2.md)