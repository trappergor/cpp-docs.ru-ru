---
title: "exp2, exp2f, exp2l | Microsoft Docs"
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
  - "exp2"
  - "exp2f"
  - "exp2l"
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
  - "exp2"
  - "math/exp2"
  - "exp2f"
  - "math/exp2f"
  - "exp2l"
  - "math/exp2l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exp2 - функция"
  - "exp2f - функция"
  - "функция exp2l"
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# exp2, exp2f, exp2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет 2 возникает с указанным значением \(например, 2ˣ\).  
  
## Синтаксис  
  
```  
double exp2(  
   double x  
);  
  
float exp2(  
   float x  
);  // C++ only  
  
long double exp2(  
   long double x  
); // C++ only  
  
float exp2f(  
   float x  
);  
  
long double exp2l(  
   long double x  
);  
  
```  
  
#### Параметры  
 \[in\] `x`  
 Значение экспоненты.  
  
## Возвращаемое значение  
 В случае успеха возвращает значение экспоненты по основанию 2 для `x` \(2ˣ\). В противном случае может возвращать одно из следующих значений:  
  
|Проблеми|Назад|  
|--------------|-----------|  
|`x` \= ±0|1|  
|`x` \= \- INFINITY|\+0|  
|`x` \= \+ INFINITY|\+ INFINITY|  
|`x` \= NaN|NaN|  
|Ошибка переполнения диапазона|\+ HUGE\_VAL \+ HUGE\_VALF, или \+ HUGE\_VALL|  
|Ошибка диапазона потери точности|правильный результат, после округления|  
  
 Сообщает об ошибках, как указано в [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `exp2` принимающие и возвращающие float и long double типов. В программе на языке C `exp2` всегда принимает и возвращает значение типа double.  
  
## Требования  
  
|Подпрограмма|Заголовок C|Заголовок C\+\+|  
|------------------|-----------------|---------------------|  
|`exp`, `expf`, `expl`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [LOG2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)