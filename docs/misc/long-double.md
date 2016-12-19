---
title: "Long Double | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.types"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "двойное с плавающей запятой длиной 10 байт"
  - "16-разрядная Windows"
  - "32-разрядная Windows"
  - "двойное с плавающей запятой длиной 8 байт"
  - "точность 80 бит"
  - "80-битная точность"
  - "двойное с плавающей запятой длиной 8 байт"
  - "long double"
ms.assetid: bb581e20-b5c2-4079-8ee8-ac6739a37852
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Long Double
Предыдущие 16\-разрядные версии Microsoft C\+\+ и Microsoft Visual C\# поддерживали `long double` — тип данных с 80\-разрядной точностью.  Однако в программировании на Win32 тип данных `double` сопоставляется с `long double` — типом данных с 64\-разрядной точностью.  Библиотека среды выполнения Microsoft предоставляет `long double` версии математических функций только для обратной совместимости.  Прототипы функций `long double` совпадают с прототипам их аналогов `double` за исключением того, что тип данных `long` `double` заменяет тип данных `double`.  Версии `long double` этих функций не должны использоваться в новом коде.  
  
### Double функции и их аналоги long double.  
  
|Функция|Long double<br /><br /> аналог|Функция|Long double<br /><br /> аналог|  
|-------------|----------------------------|-------------|----------------------------|  
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|`acosl`|[frexp](../c-runtime-library/reference/frexp.md)|`frexpl`|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|`asinl`|[\_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|`_hypotl`|  
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|`atanl`|[ldexp](../c-runtime-library/reference/ldexp.md)|`ldexpl`|  
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|`atan2l`|[log](../Topic/log,%20logf,%20log10,%20log10f.md)|`logl`|  
|[atof](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|`_atold`|[log10](../Topic/log,%20logf,%20log10,%20log10f.md)|`log10l`|  
|[Функции Бесселя: j0, j1, jn](../misc/bessel-functions-j0-j1-jn.md)|`j0l, j1l, jnl`|[\_matherr](../c-runtime-library/reference/matherr.md)|`_matherrl`|  
|[Функции Бесселя: y0, y1, yn](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|`y0l, y1l, ynl`|[modf](../c-runtime-library/reference/modf-modff-modfl.md)|`modfl`|  
|[\_cabs](../Topic/_cabs.md)|`_cabsl`|[pow](../Topic/pow,%20powf,%20powl.md)|`powl`|  
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|`ceill`|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|`sinl`|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|`cosl`|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|`sinhl`|  
|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|`coshl`|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|`sqrtl`|  
|[exp](../c-runtime-library/reference/exp-expf.md)|`expl`|[strtod](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|`_strtold`|  
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|`fabsl`|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|`tanl`|  
|[floor](../c-runtime-library/reference/floor-floorf-floorl.md)|`floorl`|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|`tanhl`|  
|[fmod](../Topic/fmod,%20fmodf.md)|`fmodl`|||  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)