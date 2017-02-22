---
title: "copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "copysignf"
  - "copysignl"
  - "_copysignl"
  - "_copysign"
  - "_copysignf"
  - "copysign"
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
  - "_copysignl"
  - "copysign"
  - "copysignf"
  - "_copysign"
  - "copysignl"
  - "_copysignf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_copysign - функция"
  - "_copysignf - функция"
  - "_copysignl - функция"
  - "copysign - функция"
  - "copysignf - функция"
  - "copysignl - функция"
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает значение, которое имеет величину одного аргумента и знак другого.  
  
## Синтаксис  
  
```  
double copysign(   
   double x,  
   double y   
);  
float copysign(   
   float x,  
   float y   
); // C++ only  
long double copysign(   
   long double x,  
   long double y   
); // C++ only  
float copysignf(   
   float x,  
   float y   
); // C++ only  
long double copysignl(   
   long double x,  
   long double y   
); // C++ only  
double _copysign(   
   double x,  
   double y   
);  
long double _copysignl(   
   long double x,  
   long double y   
);  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей точкой, которое возвращается как величина результата.  
  
 `y`  
 Значение с плавающей точкой, которое возвращается как знак результата.  
  
 [Подпрограммы поддержки чисел с плавающей точкой](../../c-runtime-library/floating-point-support.md)  
  
## Возвращаемое значение  
 Функции `copysign` возвращают значения с плавающей точкой, которое объединяет величину `x` и знак `y`.  Нет какого\-либо возврата ошибки.  
  
## Заметки  
 Поскольку C\+\+ позволяет перегрузки, можно вызывать перегрузки `copysign`, принимающие и возвращающие значения `float` или `long double`.  В программе C `copysign` всегда принимает и возвращает `double`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_copysign`|\<float.h\>|  
|`copysign`, `copysignf`, `copysignl`, `_copysignf` `_copysignl`|\<math.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [\_chgsign, \_chgsignf, \_chgsignl](../../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)