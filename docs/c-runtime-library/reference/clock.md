---
title: "часы | Microsoft Docs"
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
  - "clock"
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
  - "clock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "расчет времени использования процессора"
  - "clock - функция"
  - "время использования процессора"
  - "время использования процессора, вычисление"
  - "время, расчет процессора"
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# часы
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет реальное прошедшее время для процесса.  
  
## Синтаксис  
  
```  
clock_t clock( void );  
```  
  
## Возвращаемое значение  
 Время, прошедшее с момента запуска процесса \(затраченное время в секундах `CLOCKS_PER_SEC`\).  Если затраченное время недоступно, функция возвращает значение –1, приведенное к типу `clock_t`.  
  
## Заметки  
 Функция `clock` сообщает, сколько времени использовал вызывающий процесс.  Обратите внимание, что функция нестрого соответствует стандарту ISO C99, где возвращаемое значение — чистое время ЦП.  Чтобы получить время ЦП, используйте функцию [GetProcessTimes](http://msdn.microsoft.com/library/windows/desktop/ms683223) Win32.  
  
 Сигнал таймера примерно равен 1 \/`CLOCKS_PER_SEC` сек.  При достаточном времени значение, возвращаемое `clock`, может превысить максимальное положительное значение `clock_t` и стать отрицательным или превысить максимальное абсолютное значение, что вызовет отмену.  Не следует полагаться на это значение в качестве общего времени, затраченного на процессы, выполняющиеся более 214 748 секунд или около 59 часов.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`clock`|\<time.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_clock.c  
// This example prompts for how long  
// the program is to run and then continuously  
// displays the elapsed time for that period.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
void sleep( clock_t wait );  
  
int main( void )  
{  
   long    i = 6000000L;  
   clock_t start, finish;  
   double  duration;  
  
   // Delay for a specified time.  
   printf( "Delay for three seconds\n" );  
   sleep( (clock_t)3 * CLOCKS_PER_SEC );  
   printf( "Done!\n" );  
  
   // Measure the duration of an event.  
   printf( "Time to do %ld empty loops is ", i );  
   start = clock();  
   while( i-- )   
      ;  
   finish = clock();  
   duration = (double)(finish - start) / CLOCKS_PER_SEC;  
   printf( "%2.1f seconds\n", duration );  
}  
  
// Pauses for a specified number of milliseconds.  
void sleep( clock_t wait )  
{  
   clock_t goal;  
   goal = wait + clock();  
   while( goal > clock() )  
      ;  
}  
```  
  
  **Задержка в три секунды**  
**Готово.  Время для выполнения 6 000 000 пустых циклов составляет 0,1 сек**    
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [difftime, \_difftime32, \_difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [time, \_time32, \_time64](../Topic/time,%20_time32,%20_time64.md)