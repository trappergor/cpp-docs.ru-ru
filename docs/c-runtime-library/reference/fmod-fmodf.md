---
title: "fmod, fmodf | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fmod
- fmodf
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
- fmod
- _fmodl
- fmodf
dev_langs:
- C++
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 146a78aaa5e2cc5b3c6db716eb43c9ead91aae0b
ms.lasthandoff: 02/24/2017

---
# <a name="fmod-fmodf"></a>fmod, fmodf
Вычисляет остаток с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double fmod(   
   double x,  
   double y   
);  
float fmod(  
   float x,  
   float y   
);  // C++ only  
long double fmod(  
   long double x,  
   long double y  
);  // C++ only  
float fmodf(   
   float x,  
   float y   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`, `y`  
 Значения с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `fmod` возвращает остаток от деления `x` / `y` в виде числа с плавающей запятой. Если значение `y` равно 0,0, функция `fmod` возвращает NaN (не число) без вызова прерывания. Сведения о представлении NaN (не число) без вызова прерывания семейством функций `printf` см. в разделе [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `fmod` вычисляет остаток `f` от деления `x` / `y` в виде числа с плавающей запятой следующим образом: `x` = `i` `*` `y` + `f`, где `i` — это целое число, `f` имеет тот же знак, что и `x`, а абсолютное значение `f` меньше абсолютного значения `y`.  
  
 Так как C++ допускает перегрузку, можно вызывать перегрузки функции `fmod`. В программе на языке C `fmod` всегда принимает два и возвращает одно значение типа double.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`fmod`, `fmodf`|\<math.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_fmod.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = fmod( w, x );  
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );  
}  
```  
  
```Output  
The remainder of -10.00 / 3.00 is -1.000000  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [_CIfmod](../../c-runtime-library/cifmod.md)
