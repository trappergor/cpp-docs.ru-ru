---
title: "exp, expf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "expf"
  - "exp"
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
  - "_expl"
  - "expf"
  - "exp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "экспоненциальные вычисления"
  - "expf - функция"
  - "вычисление экспоненциальных значений"
  - "exp - функция"
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# exp, expf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет значение экспоненциальной функции.  
  
## Синтаксис  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей запятой.  
  
## Возвращаемое значение  
 Функция `exp` возвращает экспоненциальное значение параметра с плавающей точкой `x` в случае успешного выполнения.  Это значит, что результатом является e в степени `x`, где e \- это основание натурального логарифма.  При переполнении функция возвращает INF \(бесконечность\), а при потере значимости `exp` возвращает 0.  
  
|Ввод|Исключение SEH|Исключение Matherr|  
|----------|--------------------|------------------------|  
|± QNAN,IND|Нет|\_DOMAIN|  
|± ∞|INVALID|\_DOMAIN|  
|x ≥ 7.097827e\+002|INEXACT\+OVERFLOW|OVERFLOW|  
|X ≤ \-7.083964e\+002|INEXACT\+UNDERFLOW|UNDERFLOW|  
  
 `exp` имеет реализацию, которая использует набор инструкций SSE2.  Сведения и ограничения по использованию реализации SSE2 см. в разделе [\_set\_SSE2\_enable](../Topic/_set_SSE2_enable.md).  
  
## Заметки  
 C\+\+ позволяет перегрузку, поэтому можно вызвать перегрузки `exp`.  В программе на языке C `exp` всегда принимает и возвращает значение типа double.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`exp`, `expf`|\<math.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
  **exp\( 2.302585 \) \= 10.000000**   
## Эквивалент в .NET Framework  
 [System::Math::Exp](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [log, logf, log10, log10f](../Topic/log,%20logf,%20log10,%20log10f.md)   
 [\_CIexp](../Topic/_CIexp.md)