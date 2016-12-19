---
title: "fpclassify | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fpclassify"
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
apitype: "HeaderDef"
f1_keywords: 
  - "fpclassify"
  - "math/fpclassify"
helpviewer_keywords: 
  - "fpclassify-макрос"
  - "fpclassify - функция"
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fpclassify
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает классификацию аргумент с плавающей запятой.  
  
## Синтаксис  
  
```  
int fpclassify(   
   /* floating-point */ x   
);  
  
int fpclassify(   
   float x   
); // C++ only  
  
int fpclassify(   
   double x   
); // C++ only  
  
int fpclassify(   
   long double x   
); // C++ only  
  
```  
  
#### Параметры  
 `x`  
 Проверяемое значение с плавающей запятой.  
  
## Возвращаемое значение  
 `fpclassify` Возвращает целочисленное значение, указывающее, класс с плавающей точкой аргумента `x`. В этой таблице приведены возможные значения, возвращаемые `fpclassify`, определенного в \< math.h \>.  
  
|Значение|Описание|  
|--------------|--------------|  
|`FP_NAN`|Скрытый, сигналов или неопределенное значение NaN|  
|`FP_INFINITE`|Положительная или отрицательная бесконечность|  
|`FP_NORMAL`|Нормализованное значение ненулевое положительное или отрицательное|  
|`FP_SUBNORMAL`|Положительное или отрицательное значение денормализованные|  
|`FP_ZERO`|Положительное или отрицательное нулевое значение|  
  
## Заметки  
 В языке C `fpclassify` представляет собой макрос; в C\+\+, `fpclassify` является перегружен, с помощью типов аргументов функции `float`, `double`, или `long double`. В любом случае возвращаемое значение зависит от подходящий тип выражения аргумента и не все промежуточного представления. Например, обычный `double` или `long double` значение можно стать бесконечности, denormal или ноль при преобразовании в значение `float`.  
  
## Требования  
  
|Функция или макрос|Обязательный заголовок \(C\)|Обязательный заголовок \(C\+\+\)|  
|------------------------|----------------------------------|--------------------------------------|  
|`fpclassify`|\<math.h\>|\<math.h\> или \<cmath\>|  
  
 `fpclassify` Макрос и `fpclassify` соответствуют функций C \+\+ 11 спецификации и C99. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [isNaN \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)