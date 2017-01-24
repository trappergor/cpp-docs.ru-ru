---
title: "hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl | Microsoft Docs"
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
  - "_hypotf"
  - "hypot"
  - "hypotf"
  - "_hypot"
  - "_hypotl"
  - "hypotl"
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
  - "hypotf"
  - "hypotl"
  - "_hypotl"
  - "hypot"
  - "_hypot"
  - "_hypotf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_hypot - функция"
  - "вычисление гипотенуз"
  - "hypot - функция"
  - "вычисление гипотенуз"
  - "hypotf - функция"
  - "hypotl - функция"
  - "треугольники, вычисление гипотенузы"
ms.assetid: 6a13887f-bd53-43fc-9d77-5b42d6e49925
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет гипотенузу.  
  
## Синтаксис  
  
```  
double hypot(   
   double x,  
   double y   
);  
float hypotf(   
   float x,  
   float y   
);  
long double hypotl(  
   long double x,  
   long double y  
);  
double _hypot(   
   double x,  
   double y   
);  
float _hypotf(   
   float x,  
   float y   
);  
long double _hypotl(  
   long double x,  
   long double y  
);  
```  
  
#### Параметры  
 `x`, `y`  
 Значения с плавающей точкой.  
  
## Возвращаемое значение  
 В случае успеха `hypot` возвращает длину гипотенузы; при переполнении `hypot` возвращает INF \(бесконечность\) и переменная `errno` получает значение `ERANGE`.  Можно использовать `_matherr`, чтобы изменить обработку ошибок.  
  
 Дополнительные сведения о кодах возврата см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функции `hypot` вычисляют длину гипотенузы прямоугольного треугольника по длине двух сторон `x` и `y` \(другими словами, квадратный корень из `x`<sup>2</sup> \+ `y`<sup>2</sup>\).  
  
 Версии функций, которые имеют в начале имени символы подчеркивания, предоставляются для совместимости с более ранними стандартами.  Их поведение идентично версиям, не имеющим начальных символов подчеркивания.  Рекомендуется использовать версии без символов подчеркивания для нового кода.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`hypot`, `hypotf`, `hypotl`, `_hypot`, `_hypotf`, `_hypotl`|\<math.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_hypot.c  
// This program prints the hypotenuse of a right triangle.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 3.0, y = 4.0;  
  
   printf( "If a right triangle has sides %2.1f and %2.1f, "  
           "its hypotenuse is %2.1f\n", x, y, _hypot( x, y ) );  
}  
```  
  
  **If a right triangle has sides 3.0 and 4.0, its hypotenuse is 5.0**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_cabs](../Topic/_cabs.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)