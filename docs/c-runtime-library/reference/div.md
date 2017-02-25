---
title: "div | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "div"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "div"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "div - функция"
  - "деление целых чисел"
  - "частные"
  - "частные, вычисление"
  - "вычисление остатка"
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# div
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет частное и остаток двух целочисленных значений.  
  
## Синтаксис  
  
```  
div_t div(   
   int numer,  
   int denom   
);  
ldiv_t div(  
   long numer,  
   long denom  
); /* C++ only */   
lldiv_t div(  
   long long numer,  
   long long denom  
); /* C++ only */  
```  
  
#### Параметры  
 `numer`  
 Числитель.  
  
 `denom`  
 Знаменатель  
  
## Возвращаемое значение  
 `div` вызванная с использованием аргументов типа `int` возвращает структуру типа `div_t`, состоящую из частного и остатка.  Возвращаемое значение перегруженной функции с аргументами типа `long` — `ldiv_t`.  И `div_t`, и `ldiv_t` определены в STDLIB.H.  
  
## Заметки  
 Функция `div` делит `numer` на `denom` и таким образом вычисляет частное и остаток.  Структура [div\_t](../../c-runtime-library/standard-types.md) содержит частное, `int` `quot`, и остаток, `int` `rem`.  Знак частного совпадает со знаком математического частного.  Его абсолютное значение — наибольшее целое число, которое меньше абсолютного значения математического частного.  Если знаменатель — 0, программа завершается с сообщением об ошибке.  
  
 Перегруженные версии, принимающие аргументы типа `long` или `long long` доступны только для кода C\+\+.  Возвращаемый тип [ldiv\_t](../../c-runtime-library/standard-types.md) содержит элементы `long` `quot` и `long` `rem`, а возвращаемый тип [lldiv\_t](../../c-runtime-library/standard-types.md) содержит элементы `long long quot` и `long long rem`, которые имеют те же значения, что и члены `div_t`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`div`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_div.c  
// arguments: 876 13  
  
// This example takes two integers as command-line  
// arguments and displays the results of the integer  
// division. This program accepts two arguments on the  
// command line following the program name, then calls  
// div to divide the first argument by the second.  
// Finally, it prints the structure members quot and rem.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <math.h>  
  
int main( int argc, char *argv[] )  
{  
   int x,y;  
   div_t div_result;  
  
   x = atoi( argv[1] );  
   y = atoi( argv[2] );  
  
   printf( "x is %d, y is %d\n", x, y );  
   div_result = div( x, y );  
   printf( "The quotient is %d, and the remainder is %d\n",  
           div_result.quot, div_result.rem );  
}  
```  
  
  **x is 876, y is 13**  
**The quotient is 67, and the remainder is 5**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../Topic/ldiv,%20lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)