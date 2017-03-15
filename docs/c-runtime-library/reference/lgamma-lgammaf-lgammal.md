---
title: "lgamma, lgammaf, lgammal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "lgamma"
  - "lgammaf"
  - "lgammal"
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
  - "lgamma"
  - "lgammaf"
  - "lgammal"
  - "math/lgamma"
  - "math/lgammaf"
  - "math/lgammal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lgamma - функция"
  - "функция lgammal"
  - "lgammaf - функция"
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# lgamma, lgammaf, lgammal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет натуральный логарифм гамма\-функции указанное значение абсолютное значение.  
  
## Синтаксис  
  
```  
double lgamma(  
   double x  
);  
  
float lgamma(  
   float x  
); //C++ only  
  
long double lgamma(  
   long double x  
); //C++ only  
  
float lgammaf(  
   float x  
);  
  
long double lgammal(  
   long double x  
);  
  
```  
  
#### Параметры  
 \[in\] `x`  
 Значение для вычисления.  
  
## Возвращаемое значение  
 В случае успешного выполнения возвращает натуральный логарифм гамма\-функции из абсолютное значение `x.`  
  
|Проблеми|Назад|  
|--------------|-----------|  
|`x` \= NaN|NaN|  
|`x` \= ±0|\+ INFINITY|  
|`x`\= отрицательное целое число|\+ INFINITY|  
|±INFINITY|\+ INFINITY|  
|Ошибка полюс|\+ HUGE\_VAL \+ HUGE\_VALF, или \+ HUGE\_VALL|  
|Ошибка переполнения диапазона|±HUGE\_VAL, ±HUGE\_VALF или ±HUGE\_VALL|  
  
 Сообщает об ошибках, как указано в [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `lgamma` принимающие и возвращающие float и long double типов. В программе на языке C `lgamma` всегда принимает и возвращает значение типа double.  
  
 Если x является рациональное число, эта функция возвращает логарифм факториала \(`x`\-1\).  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`lgamma`, `lgammaf`,  `lgammal`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [tgamma, tgammaf, tgammal](../../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)