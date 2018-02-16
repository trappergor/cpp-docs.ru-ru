---
title: "modf, modff, modfl | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- modff
- modf
- modfl
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
dev_langs:
- C++
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9744b82cd14d29234fabf1edbe379c2c5d14ac85
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl
Разбивает значение с плавающей запятой на дробную и целую части.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double modf(  
   double x,  
   double * intptr   
);  
float modf(  
   float x,  
   float * intptr  
);  // C++ only  
long double modf(  
   long double x,  
   long double * intptr  
);  // C++ only  
float modff(  
   float x,  
   float * intptr   
);  
long double modfl(  
   long double x,  
   long double * intptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *x*  
 Значение с плавающей запятой.  
  
 `intptr`  
 Указатель на сохраненное значение целой части числа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает дробную часть числа *x* со знаком. Ошибка не возвращается.  
  
## <a name="remarks"></a>Примечания  
 Функции `modf` разбивают значение с плавающей запятой `x` на дробную и целую части, каждая из которых имеет тот же знак, что и `x`. Возвращается дробная часть числа `x` со знаком. Целая часть сохраняется как значение с плавающей запятой в `intptr.`  
  
 `modf` содержит реализацию, которая использует Streaming SIMD Extensions 2 (SSE2). Сведения о реализации SSE2 и ограничения на использование реализации SSE2 см. в разделе [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
 C++ допускает перегрузку, поэтому можно вызывать перегрузки `modf`, которые принимают и возвращают параметры `float` или `long double`. В программе на языке C `modf` всегда принимает два двойных значения и возвращает двойное значение.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`modf`, `modff`, `modfl`|C: \<math.h><br /><br /> C++: , \<cmath> или \<math.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_modf.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y, n;  
  
   x = -14.87654321;      /* Divide x into its fractional */  
   y = modf( x, &n );     /* and integer parts            */  
  
   printf( "For %f, the fraction is %f and the integer is %.f\n",   
           x, y, n );  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
For -14.876543, the fraction is -0.876543 and the integer is -14  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)