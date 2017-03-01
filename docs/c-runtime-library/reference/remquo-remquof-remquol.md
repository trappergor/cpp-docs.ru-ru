---
title: "remquo, remquof, remquol | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- remquof
- remquo
- remquol
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
- remquof
- remquol
- remquo
dev_langs:
- C++
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 304e7e441f85b329d75bc94d1ece5a84592beaf8
ms.lasthandoff: 02/24/2017

---
# <a name="remquo-remquof-remquol"></a>remquo, remquof, remquol
Вычисляет остаток от деления двух целочисленных значений и сохраняет целочисленное значение со знаком и приблизительное абсолютное значение частного в расположении, указанном в параметре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double remquo(   
   double numer,  
   double denom,  
   int* quo  
);  
float remquo(   
   float numer,  
   float denom,  
   int* quo  
); /* C++ only */  
long double remquo(   
   long double numer,  
   long double denom,  
   int* quo  
); /* C++ only */  
float remquof(   
   float numer,  
   float denom,  
   int* quo  
);  
long double remquol(   
   long double numer,  
   long double denom,  
   int* quo  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `numer`  
 Числитель.  
  
 `denom`  
 Знаменатель.  
  
 `quo`  
 Указатель на целое число для хранения значения, которое имеет знак и приблизительное абсолютное значение частного.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `remquo` возвращает остаток от деления `x` / `y` в виде числа с плавающей запятой. Если значение `y` равно 0,0, функция `remquo` возвращает NaN (не число) без вызова прерывания. Сведения о представлении NaN (не число) без вызова прерывания семейством функций `printf` см. в разделе [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `remquo` вычисляет остаток `f` от деления `x` / `y` в виде числа с плавающей запятой следующим образом: `x` = `i` `*` `y` + `f`, где `i` — это целое число, `f` имеет тот же знак, что и `x`, а абсолютное значение `f` меньше абсолютного значения `y`.  
  
 Поскольку C++ допускает перегрузку, можно вызывать перегрузки `remquo`, которые принимают и возвращают значения типов `float` или `long double`. В программе на языке C `remquo` всегда принимает два и возвращает одно значение типа double.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`remquo`, `remquof`, `remquol`|\<math.h>|  
  
 Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```C  
// crt_remquo.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
   int quo = 0;  
  
   z = remquo(w, x, &quo);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
   printf("Approximate signed quotient is %d\n", quo);  
}  
```  
  
```Output  
The remainder of -10.00 / 3.00 is -1.000000  
Approximate signed quotient is -3  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)
