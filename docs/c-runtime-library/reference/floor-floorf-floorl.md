---
title: "floor, floorf, floorl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "floorf"
  - "floorl"
  - "floor"
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
  - "floor"
  - "floorl"
  - "_floorl"
  - "floorf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "вычисление минимальных значений"
  - "floor - функция"
  - "floorf - функция"
  - "floorl - функция"
ms.assetid: e9955f70-d659-414f-8050-132e13c8ff36
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# floor, floorf, floorl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет наибольшее целое число, которое равно или меньше значения.  
  
## Синтаксис  
  
```  
double floor(  
   double x  
);  
float floor(  
   float x   
); // C++ only  
long double floor(  
   long double x  
); // C++ only  
float floorf(  
   float x  
);  
long double floorl(  
   long double x  
);  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей запятой.  
  
## Возвращаемое значение  
 Функции `floor` возвращают значение с плавающей запятой, представляющее наибольшее целое число, которое меньше или равно `x`.  Нет какого\-либо возврата ошибки.  
  
|Ввод|Исключение SEH|Исключение Matherr|  
|----------|--------------------|------------------------|  
|± QNAN,IND|Нет|\_DOMAIN|  
  
 `floor` имеет реализацию, которая использует набор инструкций SSE2.  Дополнительные сведения и ограничения по использованию реализации с SSE2 см. в разделе [\_set\_SSE2\_enable](../Topic/_set_SSE2_enable.md).  
  
## Заметки  
 C\+\+ допускает перегрузку, поэтому можно вызывать перегрузки `floor`, принимающие и возвращающие значения `float` и `long double`.  В программе C `floor` всегда принимает и возвращает `double`.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`floor`, `floorf`, `floorl`|\<math.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_floor.c  
// This example displays the largest integers  
// less than or equal to the floating-point values 2.8  
// and -2.8. It then shows the smallest integers greater  
// than or equal to 2.8 and -2.8.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double y;  
  
   y = floor( 2.8 );  
   printf( "The floor of 2.8 is %f\n", y );  
   y = floor( -2.8 );  
   printf( "The floor of -2.8 is %f\n", y );  
  
   y = ceil( 2.8 );  
   printf( "The ceil of 2.8 is %f\n", y );  
   y = ceil( -2.8 );  
   printf( "The ceil of -2.8 is %f\n", y );  
}  
```  
  
  **The floor of 2.8 is 2.000000**  
**floor от \-2.8 is \-3.000000**  
**The ceil of 2.8 is 3.000000**  
**The ceil of \-2.8 is \-2.000000**   
## Эквивалент в .NET Framework  
 [System::Math::Floor](https://msdn.microsoft.com/en-us/library/system.math.floor.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)   
 [fmod, fmodf](../Topic/fmod,%20fmodf.md)