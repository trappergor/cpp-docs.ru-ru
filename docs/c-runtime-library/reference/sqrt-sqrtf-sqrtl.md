---
title: "sqrt, sqrtf, sqrtl | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- sqrtl
- sqrtf
- sqrt
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
- sqrt
- sqrtf
- _sqrtl
dev_langs: C++
helpviewer_keywords:
- sqrtf function
- sqrt function
- sqrtl function
- _sqrtl function
- calculating square roots
- square roots, calculating
ms.assetid: 2ba9467b-f172-41dc-8f10-b86f68fa813c
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 972d3057990a5cab21f6e5b05159f9f67a8bdf98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="sqrt-sqrtf-sqrtl"></a>sqrt, sqrtf, sqrtl
Вычисляет квадратный корень.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double sqrt(  
   double x   
);  
float sqrt(  
   float x   
);  // C++ only  
long double sqrt(  
   long double x  
);  // C++ only  
float sqrtf(  
   float x   
);  
long double sqrtl(  
   long double x   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`  
 Неотрицательные значения с плавающей запятой  
  
## <a name="remarks"></a>Примечания  
 Поскольку C++ допускает перегрузку, можно вызывать перегрузки `sqrt`, которые принимают типы `float` или `long double`. В программе на языке C `sqrt` всегда принимает и возвращает `double`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функции `sqrt` возвращают квадратный корень `x`. По умолчанию, если `x` является отрицательным числом, функция `sqrt` возвращает неопределенное значение NaN.  
  
|Ввод|Исключение SEH|Исключение `_matherr`|  
|-----------|-------------------|--------------------------|  
|± QNAN,IND|Нет|_DOMAIN|  
|- ∞|Нет|_DOMAIN|  
|x < 0|Нет|_DOMAIN|  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`sqrt`, `sqrtf`, `sqrtl`|\<math.h>|\<cmath>|  
  
 Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```C  
// crt_sqrt.c  
// This program calculates a square root.  
  
#include <math.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   double question = 45.35, answer;  
   answer = sqrt( question );  
   if( question < 0 )  
      printf( "Error: sqrt returns %f\n", answer );  
   else  
      printf( "The square root of %.2f is %.2f\n", question, answer );  
}  
```  
  
```Output  
The square root of 45.35 is 6.73  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [EXP, expf, реш](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)   
 [_CIsqrt](../../c-runtime-library/cisqrt.md)