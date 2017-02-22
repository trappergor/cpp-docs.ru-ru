---
title: "asin, asinf, asinl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "asinf"
  - "asinl"
  - "asin"
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
  - "asin"
  - "asinl"
  - "asinf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "arcsine - функция"
  - "asin - функция"
  - "asinf - функция"
  - "asinl - функция"
  - "тригонометрические функции"
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# asin, asinf, asinl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет арксинус.  
  
## Синтаксис  
  
```  
double asin(   
   double x   
);  
float asin(  
   float x  
);  // C++ only  
long double asin(  
   long double x  
);  // C++ only  
float asinf (   
   float x   
);  
long double asinl(  
   long double x  
);  
```  
  
#### Параметры  
 `x`  
 Значение, для которого нужно вычислить арксинус.  
  
## Возвращаемое значение  
 Функция `asin` возвращает арксинус \(функция, обратная синусу\) `x` из диапазона от \-π\/2 до π\/2 радиан.  
  
 По умолчанию, если `x` меньше –1 или больше 1, то `asin` возвращает неопределенное значение.  
  
|Ввод|Исключение SEH|Исключение Matherr|  
|----------|--------------------|------------------------|  
|± ∞|`INVALID`|`_DOMAIN`|  
|± `QNAN`,`IND`|Нет|`_DOMAIN`|  
|&#124;x&#124;\>1|`INVALID`|`_DOMAIN`|  
  
## Заметки  
 Поскольку C\+\+ позволяет перегрузку, можно вызывать перегруженные версии `asin` с аргументами `float` и `long double`.  В программе на языке C `asin` всегда принимает и возвращает значение типа double.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`asin`, `asinf`, `asinl`|\<math.h\>|  
  
## Пример  
 Для получения дополнительной информации см. [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md).  
  
## Эквивалент в .NET Framework  
 [System::Math::Asin](https://msdn.microsoft.com/en-us/library/system.math.asin.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)