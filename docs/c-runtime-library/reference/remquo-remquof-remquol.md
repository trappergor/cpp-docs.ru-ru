---
title: remquo, remquof, remquol | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d2bcb774d7ebe7e71c3877af326177bbf8d7160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="remquo-remquof-remquol"></a>remquo, remquof, remquol

Вычисляет остаток от деления двух целочисленных значений и сохраняет целочисленное значение со знаком и приблизительное абсолютное значение частного в расположении, указанном в параметре.

## <a name="syntax"></a>Синтаксис

```C
double remquo( double numer, double denom, int* quo );
float remquof( float numer, float denom, int* quo );
long double remquol( long double numer, long double denom, int* quo );
```

```cpp
float remquo( float numer, float denom, int* quo ); /* C++ only */
long double remquo( long double numer, long double denom, int* quo ); /* C++ only */
```

### <a name="parameters"></a>Параметры

*числа*<br/>
Числитель.

*denom*<br/>
Знаменатель.

*Текущее*<br/>
Указатель на целое число для хранения значения, которое имеет знак и приблизительное абсолютное значение частного.

## <a name="return-value"></a>Возвращаемое значение

**remquo** возвращает остаток с плавающей запятой *x* / *y*. Если значение *y* равно 0,0, **remquo** возвращает несигнальным значением NaN. Сведения о представлении несигнальным значением NaN, **printf** семействах, см. в разделе [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Примечания

**Remquo** функция вычисляет остаток с плавающей запятой *f* из *x* / *y* таким образом, что *x*   =  *я* * *y* + *f*, где *я* должно быть целым числом , *f* имеет тот же знак *x*и абсолютное значение *f* меньше, чем абсолютное значение *y*.

C++ допускает перегрузки, поэтому можно вызывать перегрузки **remquo** , принимающие и возвращающие **float** или **длинные** **двойные** значения. В программе на языке C **remquo** всегда принимает два **двойные** аргументы и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|--------------|---------------------|-|
|**remquo**, **remquof**, **remquol**|\<math.h>|\<cmath> или \<math.h>|

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

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
