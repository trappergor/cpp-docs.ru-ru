---
title: "Функции Бесселя: _j0, _j1, _jn, _y0, _y1, _yn | Microsoft Docs"
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
  - "_j0"
  - "_j1"
  - "_jn"
  - "_y0"
  - "_y1"
  - "_yn"
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
  - "c.bessel"
  - "_j0"
  - "_j1"
  - "_jn"
  - "_y0"
  - "_y1"
  - "_yn"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Функции Бесселя"
  - "_j0 - функция"
  - "_j1 - функция"
  - "_jn - функция"
  - "_y0 - функция"
  - "_y1 - функция"
  - "_yn - функция"
ms.assetid: a21a8bf1-df9d-4ba0-a8c2-e7ef71921d96
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Функции Бесселя: _j0, _j1, _jn, _y0, _y1, _yn
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляют функцию Бесселя первого или второго типа порядка 0, 1 и n. ThФункции Бесселя часто используются в математике теории электромагнитных волн.  
  
## Синтаксис  
  
```  
double _j0(   
   double x   
);  
double _j1(   
   double x   
);  
double _jn(   
   int n,  
   double x   
);  
double _y0(   
   double x   
);  
double _y1(   
   double x   
);  
double _yn(   
   int n,  
   double x   
);  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей запятой.  
  
 `n`  
 Целочисленный порядок функции Бесселя.  
  
## Возвращаемое значение  
 Каждая из этих процедур возвращает функцию Бесселя `x`. Если `x` имеет отрицательное значение в функции `_y0`, `_y1` или `_yn`, процедура устанавливает `errno` в значение `EDOM`, выводит сообщение об ошибке `_DOMAIN` в `stderr` и возвращает `_HUGE_VAL`. Изменить способ обработки ошибок можно с помощью `_matherr`.  
  
## Заметки  
 Процедуры `_j0`, `_j1` и `_jn` возвращают функции Бесселя первого типа: порядка 0, 1 и n соответственно.  
  
|Ввод|Исключение SEH|Исключение Matherr|  
|----------|--------------------|------------------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
  
 Процедуры `_y0`, `_y1` и `_yn` возвращают функции Бесселя второго типа: порядка 0, 1 и n соответственно.  
  
|Ввод|Исключение SEH|Исключение Matherr|  
|----------|--------------------|------------------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
|± 0|`ZERODIVIDE`|`_SING`|  
|&#124;x&#124;\<0.0|`INVALID`|`_DOMAIN`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_j0`, `_j1`, `_jn`, `_y0`, `_y1`, `_yn`|\<cmath\> \(C\+\+\), \<math.h\> \(C, C\+\+\)|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_bessel1.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.387;  
   int n = 3, c;  
  
   printf( "Bessel functions for x = %f:\n", x );  
   printf( " Kind   Order  Function     Result\n\n" );  
   printf( " First  0      _j0( x )     %f\n", _j0( x ) );  
   printf( " First  1      _j1( x )     %f\n", _j1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " First  %d      _jn( %d, x )  %f\n", c, c, _jn( c, x ) );  
   printf( " Second 0      _y0( x )     %f\n", _y0( x ) );  
   printf( " Second 1      _y1( x )     %f\n", _y1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " Second %d      _yn( %d, x )  %f\n", c, c, _yn( c, x ) );  
}  
```  
  
```Output  
Функции Бесселя для x = 2.387000: Тип   Порядок  Функция     Результат Первый  0      _j0( x )     0.009288 Первый  1      _j1( x )     0.522941 Первый  2      _jn( 2, x )  0.428870 Первый  3      _jn( 3, x )  0.195734 Первый  4      _jn( 4, x )  0.063131 Второй 0      _y0( x )     0.511681 Второй 1      _y1( x )     0.094374 Второй 2      _yn( 2, x )  -0.432608 Второй 3      _yn( 3, x )  -0.819314 Второй 4      _yn( 4, x )  -1.626833  
```  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)