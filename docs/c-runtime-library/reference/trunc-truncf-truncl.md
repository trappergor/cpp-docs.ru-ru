---
title: "TRUNC, truncf, truncl | Microsoft Docs"
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
  - "trunc"
  - "truncf"
  - "truncl"
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
  - "trunc"
  - "truncf"
  - "truncl"
  - "math/trunc"
  - "math/truncf"
  - "math/truncl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "trunc - функция"
  - "truncf - функция"
  - "функция truncl"
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# TRUNC, truncf, truncl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет ближайшего целое число, которое меньше или равно заданному значению с плавающей запятой.  
  
## Синтаксис  
  
```  
double trunc(  
   double x  
);  
  
float trunc(  
   float x  
); //C++ only  
  
long double trunc(  
   long double x  
); //C++ only  
  
float trunc(  
   float x  
); //C++ only  
  
long double truncl(  
   long double x  
);  
  
```  
  
#### Параметры  
 \[in\] `x`  
 Значение для усечения.  
  
## Возвращаемое значение  
 В случае успеха возвращает целое значение `x`, округленные к нулю.  
  
 В противном случае может возвращать одно из следующих:  
  
|Проблеми|Назад|  
|--------------|-----------|  
|`x` \= ±INFINITY|x|  
|`x` \=  ±0|x|  
|`x` \= NaN|NaN|  
  
 Сообщает об ошибках, как указано в [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки `trunc` принимающие и возвращающие float и long double типов. В программе на языке C `trunc` всегда принимает и возвращает значение типа double.  
  
 Поскольку наибольшие значения с плавающей запятой являются точное целых чисел, эта функция не будет переполнения самостоятельно. Тем не менее может вызвать функцию к переполнению, возвращая значение в тип integer.  
  
 Можно также провести округление путем неявного преобразования из чисел с плавающей запятой в целочисленный; Тем не менее это является только значения, которые могут храниться в целевой тип.  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`trunc`, `truncf`,  `truncl`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)