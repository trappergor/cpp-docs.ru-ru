---
title: "log1p, log1pf, log1pl2 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- log1p
- log1pf
- log1pl
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 14d0228b24a97c2b7113cf9ceccf337c15ef904c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl
Вычисляет натуральный логарифм суммы указанного значения и 1.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double log1p(  
   double x  
);  
  
float log1p(  
   float x  
); //C++ only  
  
long double log1p(  
   long double x  
); //C++ only  
  
float log1pf(  
   float x  
);  
  
long double log1pl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`  
 Аргумент с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращает натуральный логарифм (по основанию e) выражения (`x`+1).  
  
 В случае неудачи может возвращать одно из следующих значений:  
  
|Ввод|Результат|Исключение SEH|errno|  
|-----------|------------|-------------------|-----------|  
|+inf|+inf|||  
|Денормализованные числа|Аналогично входным данным|UNDERFLOW||  
|±0|Аналогично входным данным|||  
|-1|-inf|DIVBYZERO|ERANGE|  
|< –1|nan|INVALID|EDOM|  
|-inf|nan|INVALID|EDOM|  
|±SNaN|Аналогично входным данным|INVALID||  
|±QNaN, indefinite|Аналогично входным данным|||  
  
 `errno` имеет значение ERANGE, если `x` = –1. `errno` EDOM присвоено значение, если `x` < -1.  
  
## <a name="remarks"></a>Примечания  
 Точность функции `log1p` можно повысить, используя выражение log(`x`+1) при значении x, близких к 0.  
  
 Так как C++ допускает перегрузку, можно вызывать перегрузки функции `log1p`, принимающие и возвращающие типы значений с плавающей запятой и длинных двойных значений. В программе на языке C `log1p` всегда принимает и возвращает двойное значение.  
  
 Если `x` является натуральным числом, эта функция возвращает логарифм факториала (`x`–1).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`log1p`,                `log1pf`, `log1pl`|\<math.h>|\<cmath>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)