---
title: "ABS, лабораторные занятия, llabs, _abs64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "abs"
  - "_abs64"
  - "labs"
  - "llabs"
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
  - "stdlib/_abs64"
  - "math/abs"
  - "_abs64"
  - "abs"
  - "labs"
  - "math/labs"
  - "llabs"
  - "math/llabs"
  - "cmath/abs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "абсолютные значения"
  - "abs - функция"
  - "abs64 - функция"
  - "_abs64 - функция"
  - "вычисление абсолютных значений"
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# ABS, лабораторные занятия, llabs, _abs64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет абсолютное значение аргумента.  
  
## Синтаксис  
  
```  
int abs(   
   int n   
);  
long abs(   
   long n   
);   // C++ only  
long long abs(   
   long long n   
);   // C++ only  
double abs(   
   double n   
);   // C++ only  
long double abs(  
   long double n  
);   // C++ only  
float abs(  
   float n   
);   // C++ only  
long labs(  
   long n   
);  
long long llabs(  
   long long n   
);  
__int64 _abs64(   
   __int64 n   
);  
```  
  
#### Параметры  
 `n`  
 Числовое значение.  
  
## Возвращаемое значение  
 `abs`, `labs`, `llabs` И `_abs64` функции возвращают абсолютное значение параметра `n`. Ошибка не возвращается.  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `abs` принимающие и возвращающие `long`, `long long`, `float`, `double`, и `long double` значения. Эти перегруженные методы определяются в заголовке \< cmath \>. В программе на языке C `abs` всегда принимает и возвращает целое число  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Поскольку диапазон отрицательных целых чисел, которые могут быть представлены с помощью любой целочисленный тип превышает диапазон положительных целых чисел, которые могут быть представлены с помощью этого типа, можно указать аргумент для этих функций, которые не могут быть преобразованы. Если абсолютное значение аргумента не может быть представлен типом возвращаемого `abs` функции возвращают значение аргумента без изменений. В частности `abs(INT_MIN)` возвращает `INT_MIN`, `labs(LONG_MIN)` возвращает `LONG_MIN`, `llabs(LLONG_MIN)` возвращает `LLONG_MIN`, и `_abs64(_I64_MIN)` возвращает `_I64_MIN`. Это означает, что `abs` функции не может использоваться для обеспечения положительное значение.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C\+\+|  
|------------------|------------------------------|----------------------------------|  
|`abs`, `labs`, `llabs`|\< math.h \> или \< stdlib.h \>|\< cmath \>, \< cstdlib \>, \< stdlib.h \> или \< math.h \>|  
|`_abs64`|\<stdlib.h\>|\< cstdlib \> или \< stdlib.h \>|  
  
 Чтобы использовать перегруженные версии `abs` в C\+\+ необходимо включить заголовок \< cmath \>.  
  
## Пример  
 Эта программа вычисляет и отображает абсолютные значения несколько чисел.  
  
```c  
// crt_abs.c  
// Build: cl /W3 /TC crt_abs.c  
// This program demonstrates the use of the abs function  
// by computing and displaying the absolute values of  
// several numbers.  
  
#include <stdio.h>  
#include <math.h>  
#include <stdlib.h>  
#include <limits.h>  
  
int main( void )  
{  
    int ix = -4;  
    long lx = -41567L;  
    long long llx = -9876543210LL;  
    __int64 wx = -1;  
  
    // absolute 32 bit integer value  
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));  
  
    // absolute long integer value  
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));  
  
    // absolute long long integer value  
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));  
  
    // absolute 64 bit integer value  
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,   
        _abs64(wx));  
  
    // Integer error cases:  
    printf_s("Microsoft implementation-specific results:\n");  
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));  
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));  
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));  
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));  
}  
```  
  
```Output  
Абсолютное значение -4 — 4, абсолютное значение-41567 является абсолютное значение-9876543210 является абсолютное значение 0xffffffffffffffff 9876543210 41567 результатов зависит от реализации Microsoft 0x0000000000000001: _abs64(_I64_MIN) возвращает -9223372036854775808 возвращает 0x8000000000000000 abs(INT_MIN) возвращает от -2147483648 labs(LONG_MIN) возвращает от -2147483648 llabs(LLONG_MIN)  
  
```  
  
## Эквивалент в .NET Framework  
 [System::Math::Abs](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_cabs](../Topic/_cabs.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [imaxabs](../Topic/imaxabs.md)