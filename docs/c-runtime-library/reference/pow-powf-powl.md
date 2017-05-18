---
title: "pow, powf, powl | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- powl
- pow
- powf
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
- powl
- pow
- _powl
- powf
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 4400582a792644b928c02db346bc7eae1087dc85
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="pow-powf-powl"></a>pow, powf, powl
Вычисляет значение `x`, возведенное в степень `y`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double pow(  
   double x,  
   double y   
);  
double pow(  
   double x,  
   int y  
);  // C++ only  
float pow(  
   float x,  
   float y   
);  // C++ only  
float pow(  
   float x,  
   int y  
);  // C++ only  
long double pow(  
   long double x,  
   long double y  
);  // C++ only  
long double pow(  
   long double x,  
   int y  
);  // C++ only  
float powf(  
   float x,  
   float y   
);  
long double powl(  
   long double x,  
   long double y  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`  
 База.  
  
 `y`  
 Экспонента.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение `x`<sup>y</sup>. Сообщение об ошибке не выводится в случае переполнения или потери значимости.  
  
|Значения x и y|Возвращаемое значение функции pow|  
|-----------------------|-------------------------|  
|`x` \< > 0 и `y` = 0.0|1|  
|`x` = 0.0 и `y` = 0.0|1|  
|`x` = 0.0 и `y` < 0|INF|  
  
## <a name="remarks"></a>Примечания  
 `pow` не распознает целочисленных значений с плавающей запятой больше 2<sup>64</sup> (например, `1.0E100`).  
  
 Функция `pow` содержит реализацию, которая использует Streaming SIMD Extensions 2 (SSE2). Сведения о реализации SSE2 и ограничениях на ее использование см. в разделе [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
 Так как C++ допускает перегрузку, можно вызывать любые перегрузки `pow`. В программе на языке C `pow` всегда принимает два и возвращает одно значение типа double.  
  
 Перегрузка `pow(int, int)` более не доступна. При использовании этой перегрузки компилятор может выдать C2668. Чтобы избежать этой проблемы, необходимо привести параметр к типу `double`, `float` или `long double`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`pow`, `powf`, `powl`|\<math.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_pow.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.0, y = 3.0, z;  
  
   z = pow( x, y );  
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
2.0 to the power of 3.0 is 8.0  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [EXP, expf, реш](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [sqrt, sqrtf, sqrtl](../../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)   
 [_CIpow](../../c-runtime-library/cipow.md)
