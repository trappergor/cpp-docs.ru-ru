---
title: "nearbyint, nearbyintf, nearbyintl | Microsoft Docs"
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
  - "nearbyint"
  - "nearbyintf"
  - "nerabyintl"
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
  - "nearbyint"
  - "nearbyintf"
  - "nearbyintl"
  - "math/nearbyint"
  - "math/narbyintf"
  - "math/narbyintl"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "nearbyint - функция"
  - "nearbyintf - функция"
  - "функция nearbyintl"
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# nearbyint, nearbyintf, nearbyintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Округляет заданное значение с плавающей запятой в целое число и возвращает это значение в формате с плавающей запятой.  
  
## Синтаксис  
  
```  
double nearbyint(  
   double x  
);  
  
float nearbyint(  
   float x  
); //C++ only  
  
long double nearbyint(  
   long double x  
); //C++ only  
  
float nearbyintf(  
   float x  
);  
  
long double nearbyintl(  
   long double x  
);  
  
```  
  
#### Параметры  
 \[in\] `x`  
 Значение для округления.  
  
## Возвращаемое значение  
 В случае успеха возвращает `x`, округленное до ближайшего целого числа, используя текущий формат округления в соответствии с fegetround. В противном случае функция может возвращать одно из следующих значений:  
  
|Проблеми|Назад|  
|--------------|-----------|  
|`x` \= ±INFINITY|±INFINITY, без изменений|  
|`x` \= ±0|±0, без изменений|  
|`x` \= NaN|NaN|  
  
 Ошибки не выводятся в [\_matherr](../../c-runtime-library/reference/matherr.md)в частности, эта функция не сообщает о FE\_INEXACT исключений.  
  
## Заметки  
 Основное различие между этой функции и `rint` является, что эта функция не вызывает неточный исключения с плавающей точки.  
  
 Поскольку максимальные значения с плавающей запятой являются точное целых чисел, эта функция будет переполнение никогда не происходит само по себе; Вместо этого выходных данных может привести к переполнению возвращаемого значения, используйте в зависимости от того, какая версия функции.  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`nearbyint`, `nearbyintf`,  `nearbyintl`|\<math.h\>|\<cmath\>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)