---
title: "_status87, _statusfp, _statusfp2 | Microsoft Docs"
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
  - "_statusfp2"
  - "_statusfp"
  - "_status87"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_statusfp2"
  - "_statusfp"
  - "statusfp2"
  - "_status87"
  - "status87"
  - "statusfp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "функции с плавающей запятой, получение слова, обозначающего статус"
  - "числа с плавающей запятой, слово, обозначающее статус"
  - "Функция status87"
  - "слово, обозначающее статус, получение числа с плавающей запятой"
  - "Функция statusfp"
  - "Функция _statusfp"
  - "Функция _statusfp2"
  - "Функция statusfp2"
  - "Функция _status87"
  - "функции с плавающей запятой"
  - "слово, обозначающее статус"
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _status87, _statusfp, _statusfp2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает слово состояния вычислительного устройства для значений с плавающей запятой.  
  
## Синтаксис  
  
```  
unsigned int _status87( void );  
unsigned int _statusfp( void );  
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)  
```  
  
#### Параметры  
 `px86`  
 Этот адрес заполняется словом состояния для устройства x87, работающего со значениями с плавающей запятой.  
  
 `pSSE2`  
 Этот адрес заполняется словом состояния для устройства SSE2, работающего со значениями с плавающей запятой.  
  
## Возвращаемое значение  
 Для `_status87` и `_statusfp` биты в возвращенном значении указывают состояние устройства.  Обратитесь к файлу FLOAT.H за определениями битов, возвращаемых `_statusfp`.  Многие математические библиотечные функции изменяют слово состояния устройства с непредсказуемыми результатами.  Оптимизация может изменить, объединить и исключить операции с плавающей запятой вокруг вызовов `_status87`, `_statusfp` и связанных функций.  Используйте параметр компилятора [\/Od \(Выключение \(отладчика\)\)](../../build/reference/od-disable-debug.md) или директиву pragma [fenv\_access](../../preprocessor/fenv-access.md) для предотвращения оптимизаций, переупорядочивающих операции с плавающей запятой.  Возвращаемые из `_clearfp` и `_statusfp` значения, а также возвращаемые параметры `_statusfp2` более надежны при меньшем числе операций с плавающей запятой, выполняющихся между известными значениями слова состояния устройства.  
  
## Заметки  
 Функция `_statusfp` получает слово состояния устройства, работающего со значениями с плавающей запятой.  Слово состояния — это сочетание состояния процессора значений с плавающей запятой и других условий, обнаруженных обработчиком исключений операций с плавающей запятой исключением, — например, переполнение стека или потеря точности.  Демаскированные исключения проверяются перед возвращением слова состояния.  Это означает, что вызывающая функция информируется о необработанных исключениях.  На платформах x86 `_statusfp` возвращает комбинацию состояний x87 и SSE2.  На платформах x64 возвращаемое состояние основывается на состоянии MXCSR SSE.  На платформах ARM `_statusfp` возвращает состояние из регистра FPSCR.  
  
 `_statusfp` \- независимая от платформы, переносимая версия `_status87`.  Она идентична `_status87` на платформах Intel \(x86\) и также поддерживается платформами ARM и x64.  Чтобы убедиться, что код, выполняющий операции с плавающей запятой, переносим на все архитектуры, используйте `_statusfp`.  Если используются только платформы x86, то можно использовать или `_status87`, или `_statusfp`.  
  
 Рекомендуется использовать `_statusfp2` для микросхем \(например Pentium IV\), обладающих и x87, и SSE2.  Для `_statusfp2`, адреса заполняются с использованием состояния как для x87, так и для SSE2.  Для микросхемы, поддерживающей x87 и SSE2 процессоры с плавающей запятой, EM\_AMBIGUOUS имеет значение 1, если `_statusfp` или `_controlfp` используются и действие было неоднозначным, поскольку оно могло ссылаться на состояние x87 или SSE2.  Функция `_statusfp2` поддерживается только на платформах x86.  
  
 Эти функции не используются для компиляции [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md) или `/clr:pure`, поскольку среда CLR \(CLR\) поддерживает только точность значений с плавающей запятой по умолчанию.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_status87`, `_statusfp`, `_statusfp2`|\<float.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_statusfp.c  
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c  
// This program creates various floating-point errors and  
// then uses _statusfp to display messages that indicate these problems.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access(on)  
  
double test( void )  
{  
   double a = 1e-40;  
   float b;  
   double c;  
  
   printf("Status = 0x%.8x - clear\n", _statusfp());  
  
   // Assignment into b is inexact & underflows:   
   b = (float)(a + 1e-40);  
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());  
  
   // c is denormal:   
   c = b / 2.0;   
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",   
            _statusfp());  
  
   // Clear floating point status:   
   _clearfp();  
   return c;  
}  
  
int main(void)  
{  
   return (int)test();  
}  
```  
  
  **Status \= 0x00000000 \- clear**  
**Status \= 0x00000003 \- inexact, underflow**  
**Status \= 0x00080003 \- inexact, underflow, denormal**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)