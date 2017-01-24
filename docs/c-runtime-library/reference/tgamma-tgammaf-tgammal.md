---
title: "tgamma, tgammaf, tgammal | Microsoft Docs"
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
  - "tgamma"
  - "tgammaf"
  - "tgammal"
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
  - "tgamma"
  - "tgammaf"
  - "tgammal"
  - "math/tgamma"
  - "math/tgammaf"
  - "math/tgammal"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "tgamma - функция"
  - "tgammaf - функция"
  - "функция tgammal"
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tgamma, tgammaf, tgammal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет гамма\-функции указанного значения.  
  
## Синтаксис  
  
```  
double tgamma(  
   double x  
);  
  
float tgamma(  
   float x  
); //C++ only  
  
long double tgamma(  
   long double x  
); //C++ only  
  
float tgammaf(  
   float x  
);  
  
long double tgammal(  
   long double x  
);  
  
```  
  
#### Параметры  
 \[in\] `x`  
 Значение для поиска гамма.  
  
## Возвращаемое значение  
 В случае успеха возвращает гамма `x`.  
  
 Ошибка диапазона может возникнуть, если величина `x` слишком велико или слишком мало для типа данных. Ошибка домена или диапазона ошибка может возникать, если `x` \< \= 0.  
  
|Проблеми|Назад|  
|--------------|-----------|  
|x \= ±0|±INFINITY|  
|x \= отрицательное целое число|NaN|  
|x \= \- INFINITY|NaN|  
|x \= \+ INFINITY|\+ INFINITY|  
|x \= NaN|NaN|  
|ошибки домена|NaN|  
|Ошибка полюс|±HUGE\_VAL, ±HUGE\_VALF или ±HUGE\_VALL|  
|Ошибка переполнения диапазона|±HUGE\_VAL, ±HUGE\_VALF или ±HUGE\_VALL|  
|Ошибка диапазона потери точности|правильное значение после округления.|  
  
 Сообщает об ошибках, как указано в [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Заметки  
 Поскольку C\+\+ допускает перегрузку, можно вызывать перегрузки tgamma, которые принимают и возвращают float и long double типов. В программе на языке C tgamma всегда принимает и возвращает значение типа double.  
  
 Если x является номером естественного, эта функция возвращает факториал числа \(x\-1\).  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`tgamma`, `tgammaf`,  `tgammal`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [lgamma, lgammaf, lgammal](../../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)