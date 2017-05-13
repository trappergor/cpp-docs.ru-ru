---
title: "remainder, remainderf, remainderl | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
dev_langs:
- C++
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: bfd25184e2542c8f1f3c4e1e975397685328b64b
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl
Вычисляет остаток от частного двух чисел с плавающей запятой, округленного до ближайшего целого значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double remainder(   
   double numer,  
   double denom  
);  
float remainder(   
   float numer,  
   float denom  
); /* C++ only */  
long double remainder(   
   long double numer,  
   long double denom  
); /* C++ only */  
float remainderf(   
   float numer,  
   float denom  
);  
long double remainderl(   
   long double numer,  
   long double denom  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `numer`  
 Числитель.  
  
 `denom`  
 Знаменатель.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Остаток от деления `x` / `y` в виде числа с плавающей запятой. Если значение `y` равно 0,0, функция `remainder` возвращает NaN (не число) без вызова прерывания. Сведения о представлении NaN (не число) без вызова прерывания семейством функций `printf` см. в разделе [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `remainder` вычисляет остаток с плавающей запятой `r` от `x` / `y`, такой, что `x` = `n` * `y` + `r`, где `n` — целое число, наиболее близкое к значению `x` / `y`, при этом `n` четное, когда &#124; `n` - `x` / `y` &#124; = 1/2. При `r` = 0 `r` имеет тот же знак, что и `x`.  
  
 Поскольку C++ допускает перегрузку, можно вызывать перегрузки `remainder`, которые принимают и возвращают значения `float` или `long double`. В программе на языке C `remainder` всегда принимает два и возвращает одно значение типа double.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`remainder`, `remainderf`, `remainderl`|\<math.h>|  
  
 Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```C  
// crt_remainder.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = remainder(w, x);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
}  
```  
  
```Output  
The remainder of -10.00 / 3.00 is -1.000000  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)
