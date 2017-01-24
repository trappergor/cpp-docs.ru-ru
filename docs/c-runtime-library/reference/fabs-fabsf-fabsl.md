---
title: "fabs, fabsf, fabsl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fabsf"
  - "fabs"
  - "fabsl"
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
  - "fabs"
  - "fabsf"
  - "fabsl"
  - "math\fabs"
  - "math\fabsf"
  - "math\fabsl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "абсолютные значения"
  - "fabsf - функция"
  - "вычисление абсолютных значений"
  - "fabs - функция"
  - "функция fabsl"
ms.assetid: 23bca210-f408-4f5e-b46b-0ccaaec31e36
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fabs, fabsf, fabsl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет абсолютное значение аргумента с плавающей точкой.  
  
## Синтаксис  
  
```  
double fabs(   
   double x   
);  
float fabs(  
   float x   
); // C++ only  
long double fabs(  
   long double x  
); // C++ only  
float fabsf(   
   float x   
);  
long double fabsl(  
   long double x  
);  
```  
  
#### Параметры  
 `x`  
 Значение с плавающей запятой.  
  
## Возвращаемое значение  
 `fabs` Функции возвращают абсолютное значение аргумента `x`. Ошибка не возвращается.  
  
|Ввод|Исключение SEH|Исключение Matherr|  
|----------|--------------------|------------------------|  
|± QNAN,IND|Нет|\_DOMAIN|  
  
## Заметки  
 C\+\+ допускает перегрузки, поэтому можно вызывать перегрузки `fabs` при включении заголовок \< cmath \>. В программе на языке C `fabs` всегда принимает и возвращает значение типа double.  
  
## Требования  
  
|Функция|Обязательный заголовок C|Обязательный заголовок C\+\+|  
|-------------|------------------------------|----------------------------------|  
|`fabs`, `fabsf`, `fabsl`|\<math.h\>|\< cmath \> или \< math.h \>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 В примере показано [abs](../../c-runtime-library/reference/abs-labs-llabs-abs64.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [ABS, лабораторные занятия, llabs, \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [\_cabs](../Topic/_cabs.md)   
 [labs, llabs](../../misc/labs-llabs.md)