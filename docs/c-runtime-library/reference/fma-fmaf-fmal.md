---
title: "FMA, fmaf, fmal | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fma"
  - "fmaf"
  - "fmal"
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
  - "fma"
  - "fmaf"
  - "fmal"
  - "math/fma"
  - "math/fmaf"
  - "math/fmal"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fma - функция"
  - "fmaf - функция"
  - "функция fmal"
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# FMA, fmaf, fmal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Перемножает два значения, добавляется третье значение и затем округляет результат, без потери точности, любой из\-за округления посредника.  
  
## Синтаксис  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### Параметры  
 \[in\] `x`  
 Первое значение для перемножения.  
  
 \[in\] `y`  
 Второе значение для перемножения.  
  
 \[in\] `z`  
 Значение для сложения.  
  
## Возвращаемое значение  
 Returns \(`x` ×    `y`\) \+ `z`. Затем возвращаемое значение округляется в текущем формате округления.  
  
 В противном случае может возвращать одно из следующих значений:  
  
|Проблеми|Назад|  
|--------------|-----------|  
|`x` \= БЕСКОНЕЧНОСТЬ, `y` \= 0 или<br /><br /> `x` \= 0, `y` \= БЕСКОНЕЧНОСТЬ|NaN|  
|`x` или `y` \= точные ± бесконечность, `z` \= бесконечность с противоположным знаком|NaN|  
|`x` или `y` \= NaN|NaN|  
|не \(`x` \= 0, `y`\= неопределенное\) и `z` \= NaN<br /><br /> не \(`x`\= неопределенное, `y`\= 0\) и `z` \= NaN|NaN|  
|Ошибка переполнения диапазона|±HUGE\_VAL, ±HUGE\_VALF или ±HUGE\_VALL|  
|Ошибка диапазона потери точности|правильное значение после округления.|  
  
 Сообщает об ошибках, как указано в [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `fma` принимающие и возвращающие float и long double типов. В программе на языке C `fma` всегда принимает и возвращает значение типа double.  
  
 Эта функция вычисляет значение, как если бы он были предприняты для бесконечного точность и затем округляет результат.  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`fma`, `fmaf`,  `fmal`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../Topic/remquo,%20remquof,%20remquol.md)