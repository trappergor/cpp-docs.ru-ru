---
title: "erf, erff, erfl, erfc, erfcf, erfcl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "erff"
  - "erfl"
  - "erf"
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
  - "erfl"
  - "erf"
  - "erff"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erf - функция"
  - "erff - функция"
  - "erfl - функция"
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# erf, erff, erfl, erfc, erfcf, erfcl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет функцию ошибок или дополнительную функцию ошибок значения.  
  
## Синтаксис  
  
```  
double erf(    double x ); float erf(    float x ); // C++ only long double erf(    long double x ); // C++ only float erff(    float x ); long double erfl(    long double x ); double erfc(    double x ); float erfc(    float x ); // C++ only long double erfc(    long double x ); // C++ only float erfcf(    float x ); long double erfcl(    long double x );  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей запятой.  
  
## Возвращаемое значение  
 Функция `erf` возвращает функцию Гаусса \(нормального распределения\) ошибок `x`.  Функция `erfc` возвращает дополнительную функцию Гаусса \(нормального распределения\) ошибок `x`.  
  
## Заметки  
 Функция `erf` вычисляет функцию Гаусса ошибок значения x, которая определяется как:  
  
 ![Функция ошибок от x](../../c-runtime-library/reference/media/crt_erf_formula.png "CRT\_erf\_formula")  
  
 Дополнительная функция Гаусса ошибок определяется как 1 \- erf\(x\).  Функция `erf` возвращает значение в диапазоне от \-1,0 до 1,0.  Ошибка не возвращается.  Функция `erfc` возвращает значение в диапазоне от 0 до 2.  Если значение `x` слишком большое для `erfc`, переменная `errno` задается равной `ERANGE`.  
  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `erf` и `erfc`, которые принимают и возвращают типы `float` и `long double`.  В программе на языке C `erf` и `erfc` всегда принимают и возвращают значение `double`.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`erf`, `erff`, `erfl`, `erfc`, `erfcf`, `erfcl`|\<math.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)