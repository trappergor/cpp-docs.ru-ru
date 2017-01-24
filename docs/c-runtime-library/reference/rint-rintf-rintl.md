---
title: "rint, rintf, rintl | Microsoft Docs"
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
  - "rintf"
  - "rintl"
  - "rint"
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
  - "rintf"
  - "rintl"
  - "rint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция rintf"
  - "Функция rint"
  - "Функция rintl"
ms.assetid: 312ae3e6-278c-459a-9393-11b8f87d9184
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rint, rintf, rintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Округляет значение с плавающей запятой до ближайшего целого числа в формате с плавающей запятой.  
  
## Синтаксис  
  
```  
double rint( double x ); float rint( float x );  // C++ only long double rint( long double x );  // C++ only float rintf( float x );  long double rintl( long double x );    
```  
  
#### Параметры  
 `x`  
 Округляемое значение с плавающей запятой.  
  
## Возвращаемое значение  
 Функции `rint` возвращают значение с плавающей запятой, которое представляет целое число, ближайшее к `x`.  Промежуточные значения округляются согласно текущей настройке режима округления чисел с плавающей запятой \(аналогично функциям `nearbyint`\).  В отличие от функций `nearbyint` функции `rint` могут вызывать исключение числа с плавающей запятой `FE_INEXACT`, если значение результата отличается от аргумента.  Ошибка не возвращается.  
  
|Ввод|Исключение SEH|Исключение `_matherr`|  
|----------|--------------------|---------------------------|  
|± ∞, QNAN, IND|Нет|Нет|  
|Денормализованные числа|EXCEPTION\_FLT\_UNDERFLOW|Нет|  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `rint`, которые принимают и возвращают значения `float` и `long double`.  В программе на языке C `rint` всегда принимает и возвращает `double`.  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`rint`, `rintf`, `rintl`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_rint.c  
// Build with: cl /W3 /Tc crt_rint.c  
// This example displays the rounded results of  
// the floating-point values 2.499999, -2.499999,   
// 2.8, -2.8, 2.5 and -2.5.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.499999;  
   float y = 2.8f;  
   long double z = 2.5;  
  
   printf("rint(%f) is %.0f\n", x, rint (x));  
   printf("rint(%f) is %.0f\n", -x, rint (-x));  
   printf("rintf(%f) is %.0f\n", y, rintf(y));  
   printf("rintf(%f) is %.0f\n", -y, rintf(-y));  
   printf("rintl(%Lf) is %.0Lf\n", z, rintl(z));  
   printf("rintl(%Lf) is %.0Lf\n", -z, rintl(-z));  
}  
```  
  
  **rint\(2,499999\) is 2rint\(\-2.499999\) is \-2rintf\(2,800000\) is 3rintf\(\-2.800000\) is \-3rintl\(2,500000\) is 3rintl\(\-2.500000\) is \-3**   
## Эквивалент в .NET Framework  
 [System::Math::Round](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../Topic/fmod,%20fmodf.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](http://msdn.microsoft.com/ru-ru/312fd869-a9c0-4107-bb23-ab8299d04385)   
 [lround, lroundf, lroundl, llround, llroundf, llroundl](../../c-runtime-library/reference/lround-lroundf-lroundl-llround-llroundf-llroundl.md)   
 [nearbyint, nearbyintf, nearbyintl](http://msdn.microsoft.com/ru-ru/15111e73-331d-41d1-81b7-3e10df894848)   
 [rint](../../c-runtime-library/reference/rint-rintf-rintl.md)