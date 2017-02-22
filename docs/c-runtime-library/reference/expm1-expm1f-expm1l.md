---
title: "expm1, expm1f, expm1l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "expm1l"
  - "expm1"
  - "expm1f"
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
  - "expm1l"
  - "expm1"
  - "expm1f"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "expm1 - функция"
  - "expm1f - функция"
  - "expm1l - функция"
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# expm1, expm1f, expm1l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет экспоненциальный показатель по основанию e значения минус единица.  
  
## Синтаксис  
  
```  
double expm1(   
   double x   
);  
float expm1(  
   float x  
);  // C++ only  
long double expm1(  
   long double x  
);  // C++ only  
float expm1f(  
   float x  
);  
long double expm1l(  
   long double x  
);  
```  
  
#### Параметры  
 `x`  
 Экспоненциальное значение с плавающей запятой.  
  
## Возвращаемое значение  
 Функции `expm1` возвращают значение с плавающей запятой, представляющее e<sup>x</sup> — 1, при успешном выполнении.  При переполнении `expm1` возвращает значение `HUGE_VAL`, `expm1f` возвращает значение `HUGE_VALF`, `expm1l` возвращает `HUGE_VALL`, а параметр `errno` имеет значение `ERANGE`.  Дополнительные сведения о кодах возврата см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Поскольку C\+\+ позволяет перегрузки, можно вызывать перегрузки `expm1`, принимающие и возвращающие значения `float` и `long double`.  В программе C `expm1` всегда принимает и возвращает `double`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`expm1`, `expm1f`, `expm1l`|\<math.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [exp2, exp2f, exp2l](http://msdn.microsoft.com/ru-ru/a7974629-be1e-4196-a562-6624a0732003)   
 [pow, powf, powl](../Topic/pow,%20powf,%20powl.md)