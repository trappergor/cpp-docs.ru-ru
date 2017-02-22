---
title: "logb, logbf, logbl, _logb, _logbf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "logb"
  - "_logb"
  - "_logbl"
  - "logbf"
  - "logbl"
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
  - "logb"
  - "logbl"
  - "_logb"
  - "_logbf"
  - "logbf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_logb - функция"
  - "_logbf - функция"
  - "показатель степени, числа с плавающей запятой"
  - "степени и мантиссы"
  - "функции с плавающей запятой"
  - "функции с плавающей запятой, мантисса и степень"
  - "logb - функция"
  - "logbf - функция"
  - "logbl - функция"
  - "мантисса, переменные с плавающей запятой"
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# logb, logbf, logbl, _logb, _logbf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает значение экспоненты аргумента с плавающей точкой.  
  
## Синтаксис  
  
```  
double logb(  
   double x   
);  
float logb(  
   float x   
); // C++ only  
long double logb(  
   long double x   
); // C++ only   
float logbf(  
   float x   
);  
long double logbl(  
   long double x   
);  
double _logb(  
   double x   
);  
float _logbf(  
   float x   
);  
```  
  
#### Параметры  
 x  
 Значение с плавающей запятой.  
  
## Возвращаемое значение  
 `logb` возвращает несмещенное значение экспоненты `x` как целое число со знаком, представленное как значение с плавающей точкой.  
  
## Заметки  
 Функции `logb` извлекают экспоненциальное значение аргумента `x` с плавающей точкой, как если бы `x` было представлено с бесконечным диапазоном.  Если аргумент `x` денормализован, он обрабатывается, как если бы он был нормализован.  
  
 Поскольку C\+\+ позволяет перегрузки, можно вызывать перегрузки `logb`, принимающие и возвращающие значения `float` или `long double`.  В программе C `logb` всегда принимает и возвращает `double`.  
  
|Ввод|Исключение SEH|Исключение Matherr|  
|----------|--------------------|------------------------|  
|± QNAN,IND|Нет|\_DOMAIN|  
|± 0|ZERODIVIDE|\_SING|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_logb`|\<float.h\>|  
|`logb`, `logbf`, `logbl`, `_logbf`|\<math.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)