---
title: "LOG2, log2f, log2l | Microsoft Docs"
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
  - "log2"
  - "log2l"
  - "log2f"
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
dev_langs: 
  - "C"
  - "C++"
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LOG2, log2f, log2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет двоичный логарифм \(по основанию 2\) указанное значение.  
  
## Синтаксис  
  
```  
double log2(  
   double x  
);  
  
float log2(  
   float x  
); //C++ only  
  
long double log2(  
   long double x  
); //C++ only  
  
float log2f(  
   float x  
);  
  
long double log2l(  
   long double x  
);  
  
```  
  
#### Параметры  
 \[in\] `x`  
 Значение, чтобы определить логарифм по основанию 2.  
  
## Возвращаемое значение  
 В случае успешного выполнения возвращает log2 `x`.  
  
 В противном случае может возвращать одно из следующих значений:  
  
|Проблеми|Назад|  
|--------------|-----------|  
|`x` \< 0|NaN|  
|`x` \= ±0|\-INFINITY|  
|`x` \= 1|\+0|  
|\+ INFINITY|\+ INFINITY|  
|NaN|NaN|  
|ошибки домена|NaN|  
|Ошибка полюс|\-HUGE\_VAL, \- HUGE\_VALF, или \- HUGE\_VALL|  
  
 Сообщает об ошибках, как указано в [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Заметки  
 Если x является целым, эта функция фактически возвращает отсчитываемый от нуля индекс значащий бит 1 `x`.  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`log2`, `log2f`,  `log2l`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp2, exp2f, exp2l](../../c-runtime-library/reference/exp2-exp2f-exp2l.md)   
 [log, logf, log10, log10f](../Topic/log,%20logf,%20log10,%20log10f.md)