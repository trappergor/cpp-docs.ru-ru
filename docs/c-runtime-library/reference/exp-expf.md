---
title: "EXP, expf, реш | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- expf
- expl
- exp
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
- _expl
- expf
- expl
- exp
dev_langs: C++
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4b63b99f7451d2fbb1a0e4137469a0c4f5b01046
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="exp-expf-expl"></a>EXP, expf, реш
Вычисляет экспоненту.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
long double expl(  
   long double x  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `x`  
 С плавающей запятой значение exponentiate натурального логарифма *e* по.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `exp` Функции возвращают значение экспоненты с плавающей запятой параметра *x*, в случае успешного выполнения. Результатом является *e*<sup>*x*</sup>, где *e* является основанием натурального логарифма. На переполнение, функция возвращает INF (бесконечность) и потери значимости `exp` возвращает 0.  
  
|Ввод|Исключение SEH|Исключение Matherr|  
|-----------|-------------------|-----------------------|  
|± Несигнальным значением NaN, неопределенным|Нет|_DOMAIN|  
|Бесконечности ±|INVALID|_DOMAIN|  
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|  
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|  
  
 `exp` Функция имеет реализацию, которая использует Streaming SIMD Extensions 2 (SSE2). Сведения о реализации SSE2 и ограничения на использование реализации SSE2 см. в разделе [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
## <a name="remarks"></a>Примечания  
 C++ допускает перегрузки, поэтому можно вызывать перегрузки `exp` , которые принимают **float** или **long double** аргумент. В программе на языке C `exp` всегда принимает и возвращает **двойные**.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок C|Обязательный заголовок C++|  
|--------------|---------------------|---|  
|`exp`, `expf`|\<math.h>|\<cmath> или \<math.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
exp( 2.302585 ) = 10.000000  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [_CIexp](../../c-runtime-library/ciexp.md)