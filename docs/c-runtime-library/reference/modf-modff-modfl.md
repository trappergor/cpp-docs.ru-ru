---
title: "modf, modff, modfl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "modff"
  - "modf"
  - "modfl"
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
  - "modff"
  - "_modfl"
  - "modf"
  - "modfl"
  - "math/modf"
  - "math/modff"
  - "math/modfl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modf - функция"
  - "modff - функция"
  - "функция modfl"
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# modf, modff, modfl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Разбивает значение с плавающей запятой в долях и целое число частей.  
  
## Синтаксис  
  
```  
double modf(  
   double x,  
   double * intptr   
);  
float modf(  
   float x,  
   float * intptr  
);  // C++ only  
long double modf(  
   long double x,  
   long double * intptr  
);  // C++ only  
float modff(  
   float x,  
   float * intptr   
);  
long double modfl(  
   long double x,  
   long double * intptr  
);  
```  
  
#### Параметры  
 *x*  
 Значение с плавающей запятой.  
  
 `intptr`  
 Указатель на целое число хранимых часть.  
  
## Возвращаемое значение  
 Эта функция возвращает подписанный дробной части числа *x*. Ошибка не возвращается.  
  
## Заметки  
 `modf` Функции разбиения значение с плавающей запятой `x` в дробных частей целое число со знаком, каждый из которых имеет тот же знак, что и `x`. Подписанные дробной части числа `x` возвращается. Целая часть результата сохраняется как значение с плавающей запятой в `intptr.`  
  
 `modf` содержит реализацию, использующий Streaming SIMD Extensions 2 \(SSE2\). В разделе [\_set\_SSE2\_enable](../Topic/_set_SSE2_enable.md) сведения и ограничения на использование реализации SSE2.  
  
 C\+\+ допускает перегрузки, поэтому можно вызывать перегрузки `modf` принимающие и возвращающие `float` или `long double` Параметры. В программе на языке C `modf` всегда принимает два значения типа double и возвращает значение типа double.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`modf`, `modff`, `modfl`|C: \< math.h \><br /><br /> C\+\+:, \< cmath \> или \< math.h \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_modf.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y, n;  
  
   x = -14.87654321;      /* Divide x into its fractional */  
   y = modf( x, &n );     /* and integer parts            */  
  
   printf( "For %f, the fraction is %f and the integer is %.f\n",   
           x, y, n );  
}  
```  
  
## Вывод  
  
```  
For -14.876543, the fraction is -0.876543 and the integer is -14  
```  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)