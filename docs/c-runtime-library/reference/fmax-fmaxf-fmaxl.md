---
title: "fmax, fmaxf, fmaxl | Microsoft Docs"
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
  - "fmax"
  - "fmaxf"
  - "fmaxl"
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
  - "fmax"
  - "fmaxf"
  - "fmaxl"
  - "math/fmax"
  - "math/fmaxf"
  - "math/fmaxl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fmax - функция"
  - "fmaxf - функция"
  - "функция fmaxl"
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# fmax, fmaxf, fmaxl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определите большее из двух указанного числовых значений.  
  
## Синтаксис  
  
```  
double fmax(  
   double x,   
   double y  
);  
  
float fmax(  
   float x,   
   float y  
); //C++ only  
  
long double fmax(  
   long double x,   
   long double y  
); //C++ only  
  
float fmaxf(  
   float x,   
   float y  
);  
  
long double fmaxl(  
   long double x,   
   long double y  
);  
  
```  
  
#### Параметры  
 \[in\] `x`  
 Первое сравниваемое значение.  
  
 \[in\] `y`  
 Второе сравниваемое значение.  
  
## Возвращаемое значение  
 В случае успешного выполнения возвращает большее из `x` или `y`. Значение, возвращаемое точное и не зависит от формы округления.  
  
 В противном случае может возвращать одно из следующих значений:  
  
|Проблеми|Назад|  
|--------------|-----------|  
|`x` \= NaN|`y`|  
|`y` \= NaN|`x`|  
|`x` и `y` \= NaN|NaN|  
  
 Эта функция не использует ошибки, указанной в  [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки fmax, которые принимают и возвращают float и long double типов. В программе на языке C fmax всегда принимает и возвращает значение типа double.  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`fmax`, `fmaxf`, `fmaxl`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmin, fminf, fminl](../Topic/fmin,%20fminf,%20fminl1.md)