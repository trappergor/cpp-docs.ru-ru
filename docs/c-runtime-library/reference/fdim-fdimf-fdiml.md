---
title: "fdim, fdimf, fdiml | Microsoft Docs"
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
  - "fdim"
  - "fdimf"
  - "fdiml"
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
  - "fdim"
  - "fdimf"
  - "fdiml"
  - "math/fdim"
  - "math/fdimf"
  - "math/fdiml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fdim - функция"
  - "fdimf - функция"
  - "функция fdiml"
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# fdim, fdimf, fdiml
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет положительное разницу между значениями первого и второго.  
  
## Синтаксис  
  
```  
double fdim(  
   double x,   
   double y  
);  
  
float fdim(  
   float x,   
   float y  
); //C++ only  
  
long double fdim(  
   long double x,   
   long double y  
); //C++ only  
  
float fdimf(  
   float x,   
   float y  
);  
  
long double fdiml(  
   long double x,   
   long double y  
);  
  
```  
  
#### Параметры  
 \[in\] `x`  
 Первое значение в вычитании.  
  
 \[in\] `y`  
 Второе значение в вычитании.  
  
## Возвращаемое значение  
 Возвращает положительное разницу между `x` и `y`:  
  
|Возвращаемое значение|Сценарий|  
|---------------------------|--------------|  
|x\-y|Если x \> y|  
|0|Если x \< \= y|  
  
 В противном случае может возвращать одно из следующих ошибок:  
  
|Проблеми|Назад|  
|--------------|-----------|  
|Ошибка переполнения диапазона|\+ HUGE\_VAL \+ HUGE\_VALF, или \+ HUGE\_VALL|  
|Ошибка диапазона потери точности|правильное значение \(после округления\)|  
|`x` или `y` является NaN|NaN|  
  
 Сообщает об ошибках, как указано в [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `fdim` принимающие и возвращающие float и long double типов. В программе на языке C `fdim` всегда принимает и возвращает значение типа double.  
  
 За исключением обработки NaN, эта функция эквивалентна [fmax, fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)\(`x`\-`y,` 0\).  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`fdim`, `fdimf`,  `fdiml`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmax, fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)   
 [ABS, лабораторные занятия, llabs, \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)