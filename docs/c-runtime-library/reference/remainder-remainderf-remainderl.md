---
title: "remainder, remainderf, remainderl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "remainderl"
  - "remainder"
  - "remainderf"
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
  - "remainderf"
  - "remainder"
  - "remainderl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remainderf"
  - "remainderl"
  - "remainder"
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# remainder, remainderf, remainderl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет остаток от округленного частного двух чисел с плавающей точкой.  
  
## Синтаксис  
  
```  
double remainder(   
   double numer,  
   double denom  
);  
float remainder(   
   float numer,  
   float denom  
); /* C++ only */  
long double remainder(   
   long double numer,  
   long double denom  
); /* C++ only */  
float remainderf(   
   float numer,  
   float denom  
);  
long double remainderl(   
   long double numer,  
   long double denom  
);  
  
```  
  
#### Параметры  
 `numer`  
 Числитель.  
  
 `denom`  
 Знаменатель  
  
## Возвращаемое значение  
 Остаток от деления `x` \/ `y`, являющийся числом с плавающей точкой.  Если значение `y` равно 0,0, `remainder` возвращает NaN в тихом режиме.  Сведения о представлении NaN в тихом режиме.семейством `printf` см. в разделе [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## Заметки  
 Функция `remainder` вычисляет остаток с плавающей точкой `r` от `x` \/ `y` такой, что `x` \= `n` \* `y` \+ `r`, где `n` \- целое число, наиболее близкое к значению `x` \/ `y`, и `n` четное, когда &#124; `n` \- `x` \/ `y` &#124; \= 1\/2.  При `r` \= 0, `r` имеет тот же знак, что и `x`.  
  
 Поскольку C\+\+ позволяет перегрузки, можно вызывать перегрузки `remainder`, принимающие и возвращающие значения `float` или `long double`.  В программе на языке C `remainder` всегда принимает два значения double и возвращает значение double.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`remainder`, `remainderf`, `remainderl`|\<math.h\>|  
  
 Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```c  
// crt_remainder.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = remainder(w, x);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
}  
```  
  
  **Остаток \-10,00 \/ 3,00 равно \-1,000000**   
## Эквивалент в .NET Framework  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../Topic/ldiv,%20lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod, fmodf](../Topic/fmod,%20fmodf.md)   
 [remquo, remquof, remquol](../Topic/remquo,%20remquof,%20remquol.md)