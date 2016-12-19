---
title: "_fpclass _fpclassf | Microsoft Docs"
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
  - "_fpclass"
  - "_fpclassf"
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
  - "fpclass"
  - "_fpclass"
  - "_fpclassf"
  - "math/_fpclass"
  - "float/_fpclass"
  - "math/_fpclassf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fpclass - функция"
  - "числа с плавающей запятой, IEEE-представление"
  - "_fpclass - функция"
  - "функция _fpclassf"
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fpclass _fpclassf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает значение, указывающее классификации аргумент с плавающей запятой.  
  
## Синтаксис  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### Параметры  
 `x`  
 Проверяемое значение с плавающей запятой.  
  
## Возвращаемое значение  
 `_fpclass` И `_fpclassf` функции возвращают целое число, указывающее аргумент с плавающей запятой классификации `x`. Классификация может иметь одно из следующих значений, определенных в \< float.h \>.  
  
|Значение|Описание|  
|--------------|--------------|  
|`_FPCLASS_SNAN`|Сигнальный NaN|  
|`_FPCLASS_QNAN`|Тихий NaN|  
|`_FPCLASS_NINF`|Отрицательная бесконечность \(– INF\)|  
|`_FPCLASS_NN`|Отрицательное нормализованы ненулевое значение|  
|`_FPCLASS_ND`|Ненормализованный отрицательное|  
|`_FPCLASS_NZ`|Отрицательный ноль \(— 0\)|  
|`_FPCLASS_PZ`|0 положительное \(\+ 0\)|  
|`_FPCLASS_PD`|Ненормализованный положительные|  
|`_FPCLASS_PN`|Положительный нормализованы ненулевое значение|  
|`_FPCLASS_PINF`|Плюс бесконечность \(\+ INF\)|  
  
## Заметки  
 `_fpclass` И `_fpclassf` функции, определенные Майкрософт. Они похожи на [fpclassify](../../c-runtime-library/reference/fpclassify.md), но возвращает подробные сведения об аргументе.`_fpclassf` Функция доступна только при компиляции для x64 платформы.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_fpclass`|\<float.h\>|  
  
 Дополнительные сведения о совместимости и соответствия, в разделе [совместимости](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [isNaN \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)