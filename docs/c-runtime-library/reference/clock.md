---
title: "clock | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- clock
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clock
dev_langs:
- C++
helpviewer_keywords:
- processor time used, calculating
- time, calculating processor
- clock function
- processor time used
- calculating processor time used
ms.assetid: 3e1853dd-498f-49ba-b06a-f2315f20904e
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3a226377499df1747a022325b762b3cdfdd35ea6
ms.lasthandoff: 02/24/2017

---
# <a name="clock"></a>часы
Вычисляет реальное прошедшее время для процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
clock_t clock( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
Время, прошедшее с момента инициализации CRT в начале процесса, составляющее `CLOCKS_PER_SEC` единиц в секунду. Если прошедшее время недоступно или превышает максимальное положительное время, которое может быть записано как тип `clock_t`, функция возвращает значение `(clock_t)(-1)`.   
  
## <a name="remarks"></a>Примечания  
Функция `clock` сообщает реальное время, прошедшее с момента инициализации CRT при запуске процесса. Обратите внимание на то, что эта функция не является строго соответствующей стандарту ISO C, который определяет возвращаемое значение как чистое время ЦП. Чтобы получить время ЦП, используйте функцию [GetProcessTimes](https://msdn.microsoft.com/library/windows/desktop/ms683223) Win32. Чтобы определить прошедшее время в секундах, разделите значение, возвращаемое функцией `clock`, на макрос `CLOCKS_PER_SEC`.  
  
Если времени достаточно, значение, возвращаемое функцией `clock`, может превышать максимальное положительное значение `clock_t`. Если процесс выполняется дольше, значение, возвращаемое функций `clock`, всегда равно `(clock_t)(-1)` в соответствии со стандартами ISO C99 (7.23.2.1) и ISO C11 (7.27.2.1). Корпорация Майкрософт реализует `clock_t` как `long`, 32-разрядное целое число со знаком, а макрос `CLOCKS_PER_SEC` определяется как 1000. Это дает максимальное возвращаемое значение функции `clock`, равное 2 147 483,647 секунды или около 24,8 дня. Не следует полагаться на значение, возвращаемое `clock` в процессах, которые выполняются дольше указанного периода времени. Для записи времени, затраченного на выполнение процессов за много лет, можно использовать 64-разрядную функцию `time` или функцию Windows [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904).  

## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`clock`|\<time.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_clock.c  
// This sample uses clock() to 'sleep' for three 
// seconds, then determines how long it takes  
// to execute an empty loop 600000000 times.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
  
// Pauses for a specified number of milliseconds.  
void do_sleep( clock_t wait )  
{  
   clock_t goal;  
   goal = wait + clock();  
   while( goal > clock() )  
      ;  
}  
  
const long num_loops = 600000000L;

int main( void )  
{  
   long    i = num_loops;  
   clock_t start, finish;  
   double  duration;  
  
   // Delay for a specified time.  
   printf( "Delay for three seconds\n" );  
   do_sleep( (clock_t)3 * CLOCKS_PER_SEC );  
   printf( "Done!\n" );  
  
   // Measure the duration of an event.  
   start = clock();  
   while( i-- )   
      ;  
   finish = clock();  
   duration = (double)(finish - start) / CLOCKS_PER_SEC;  
   printf( "Time to do %ld empty loops is ", num_loops );  
   printf( "%2.3f seconds\n", duration );  
}  
```  
  
```Output  
Delay for three seconds  
Done!  
Time to do 600000000 empty loops is 1.354 seconds  
```  
  
## <a name="see-also"></a>См. также  
 [Управление временем](../../c-runtime-library/time-management.md)   
 [difftime, _difftime32, _difftime64](../../c-runtime-library/reference/difftime-difftime32-difftime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
