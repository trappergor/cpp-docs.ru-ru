---
title: "difftime, _difftime32, _difftime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_difftime32"
  - "difftime"
  - "_difftime64"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_difftime64"
  - "difftime"
  - "difftime64"
  - "_difftime32"
  - "difftime32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция _difftime32"
  - "Функция difftime"
  - "время, определение разницы"
  - "Функция difftime64"
  - "Функция _difftime64"
  - "Функция difftime32"
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# difftime, _difftime32, _difftime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Находит разность между двумя моментами времени.  
  
## Синтаксис  
  
```  
double difftime(   
   time_t timer1,  
   time_t timer0   
);  
double _difftime32(   
   __time32_t timer1,  
   __time32_t timer0   
);  
double _difftime64(   
   __time64_t timer1,  
   __time64_t timer0   
);  
```  
  
#### Параметры  
 `timer1`  
 Время окончания.  
  
 `timer0`  
 Время начала.  
  
## Возвращаемое значение  
 `difftime` Возвращает интервал времени в секундах, `timer0` к `timer1`. Возвращаемое значение с плавающей запятой двойной точности с плавающей запятой. Возвращаемое значение может быть 0, указывает на ошибку.  
  
## Заметки  
 `difftime` Функция вычисляет разницу между двумя значениями времени, предоставленного `timer0` и `timer1`.  
  
 Указано значение времени должно попадать в диапазон `time_t`.`time_t` Представляет 64\-разрядное значение. Таким образом конец диапазона была расширена с 23:59:59 18 января 2038 года, UTC для 23:59:59 31 декабря 3000. Ниже диапазона `time_t` по\-прежнему полуночи 1 января 1970 года.  
  
 `difftime` является встроенная функция, которая вычисляет либо `_difftime32` или `_difftime64` в зависимости от того, следует ли `_USE_32BIT_TIME_T` определен. \_difftime32 и \_difftime64 можно использовать непосредственно для принудительного использования определенного размера типа времени.  
  
 Эти функции проверяют свои параметры. Если параметр равен нулю или отрицательное значение, обработчик недопустимого параметра вызывается, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают 0 и задайте `errno` для `EINVAL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`difftime`|\<time.h\>|  
|`_difftime32`|\<time.h\>|  
|`_difftime64`|\<time.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```cpp  
// crt_difftime.c  
// This program calculates the amount of time  
// needed to do a floating-point multiply 100 million times.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
#include <float.h>  
  
double RangedRand( float range_min, float range_max)  
{  
   // Generate random numbers in the half-closed interval  
   // [range_min, range_max). In other words,  
   // range_min <= random number < range_max  
   return ((double)rand() / (RAND_MAX + 1) * (range_max - range_min)  
            + range_min);  
}  
  
int main( void )  
{  
   time_t   start, finish;  
   long     loop;  
   double   result, elapsed_time;  
   double   arNums[3];  
  
   // Seed the random-number generator with the current time so that  
   // the numbers will be different every time we run.  
   srand( (unsigned)time( NULL ) );  
  
   arNums[0] = RangedRand(1, FLT_MAX);  
   arNums[1] = RangedRand(1, FLT_MAX);  
   arNums[2] = RangedRand(1, FLT_MAX);  
   printf( "Using floating point numbers %.5e %.5e %.5e\n", arNums[0], arNums[1], arNums[2] );  
  
   printf( "Multiplying 2 numbers 100 million times...\n" );  
  
   time( &start );  
   for( loop = 0; loop < 100000000; loop++ )  
      result = arNums[loop%3] * arNums[(loop+1)%3];   
   time( &finish );  
  
   elapsed_time = difftime( finish, start );  
   printf( "\nProgram takes %6.0f seconds.\n", elapsed_time );  
}  
  
```  
  
```Output  
С помощью случайных чисел с плавающей запятой числа 1.04749e + 038 2.01482e 038 1.72737e + 038Multiplying 2 с плавающей запятой числа 100 миллионов раз... Программа принимает 3 секунды. Умножение 2 плавающей точки номера 500 миллионов раз... Программа занимает 5 секунд.  
```  
  
## Эквивалент в .NET Framework  
 [System::DateTime::Subtract](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Управление временем](../../c-runtime-library/time-management.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)