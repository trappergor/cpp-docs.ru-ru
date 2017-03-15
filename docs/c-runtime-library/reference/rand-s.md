---
title: "rand_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "rand_s"
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
  - "rand_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "криптографически безопасные случайные числа"
  - "генерация псевдослучайных чисел"
  - "числа, генерация псевдослучайных"
  - "числа, псевдослучайный"
  - "псевдослучайные числа"
  - "rand_s - функция"
  - "случайные числа, криптографически безопасные"
  - "случайные числа, создание"
ms.assetid: d6a0be60-997d-4904-8411-8aea6839cc94
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# rand_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает псевдослучайное число.  Это версия [rand](../Topic/rand.md) с усовершенствованиями безопасности, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t rand_s(   unsigned int* randomValue);  
```  
  
## Возвращаемое значение  
 Ноль в случае успешного выполнения, в противном случае — код ошибки.  Если параметр `randomValue` является нулевым указателем, функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение разрешено для продолжить, функция возвращает `EINVAL` и задает `errno` в `EINVAL`.  Если функция завершается с ошибкой по какой\-либо другой причине, \*`randomValue` присваивается значение 0.  
  
## Заметки  
 Функция `rand_s` записывает псевдослучайное целое число в диапазоне от 0 до `UINT_MAX` по входному указателю.  Функция `rand_s` используется операционной системой для создания криптографически безопасных случайных чисел.  В ней не используется начальное значение, созданное функцией [srand](../../c-runtime-library/reference/srand.md), и она не влияет на последовательность случайных чисел, используемую `rand`.  
  
 Функция `rand_s` требует, чтобы константа `_CRT_RAND_S` определена до включения функции, как показано в следующем примере:  
  
```  
#define _CRT_RAND_S  
#include <stdlib.h>  
```  
  
 `rand_s` зависит от API [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694), который доступен только в Windows XP или более поздних версиях.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`rand_s`|\<stdlib.h\>|  
  
 Для получения дополнительной информации см. [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_rand_s.c  
// This program illustrates how to generate random  
// integer or floating point numbers in a specified range.  
  
// Remembering to define _CRT_RAND_S prior  
// to inclusion statement.  
#define _CRT_RAND_S  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <limits.h>  
  
int main( void )  
{  
    int             i;  
    unsigned int    number;  
    double          max = 100.0;  
    errno_t         err;  
  
    // Display 10 random integers in the range [ 1,10 ].  
    for( i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %u\n", (unsigned int) ((double)number /  
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);  
    }  
  
    printf_s("\n");  
  
    // Display 10 random doubles in [0, max).  
    for (i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %g\n", (double) number /   
                          ((double) UINT_MAX + 1) * max );  
    }  
}  
```  
  
## Пример результатов выполнения  
  
```  
10  
4  
5  
2  
8  
2  
5  
6  
1  
1  
  
32.6617  
29.4471  
11.5413  
6.41924  
20.711  
60.2878  
61.0094  
20.1222  
80.9192  
65.0712  
```  
  
## Эквивалент в .NET Framework  
 [System::Random Class](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [srand](../../c-runtime-library/reference/srand.md)