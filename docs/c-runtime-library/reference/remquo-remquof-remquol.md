---
title: remquo, remquof, remquol
ms.date: 4/2/2020
api_name:
- remquof
- remquo
- remquol
- _o_remquo
- _o_remquof
- _o_remquol
api_location:
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- remquof
- remquol
- remquo
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
ms.openlocfilehash: d1b5c60e2e6bd8ba4d5f3b4297dff4bd57c650f2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216795"
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

*число ключей*<br/>
Числитель.

*деном*<br/>
Знаменатель.

*кво*<br/>
Указатель на целое число для хранения значения, которое имеет знак и приблизительное абсолютное значение частного.

## <a name="return-value"></a>Возвращаемое значение

**remquo** возвращает остаток от деления *x*y на значение с плавающей запятой  /  *y*. Если значение *y* равно 0,0, **remquo** возвращает нетихом NaN. Сведения о представлении нескрытого числа NaN в семействе **printf** см. в разделе [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Remarks

Функция **remquo** вычисляет *f* y остатка с плавающей запятой *x*  /  *y* таким образом, что *x*  =  *i* \* *y*  +  *f*, где *i* является целым числом, *f* имеет тот же знак, что и *x*, а абсолютное значение *f* меньше, чем абсолютное значение *y*.

C++ допускает перегрузку, поэтому можно вызывать перегрузки **remquo** , которые принимают и возвращают **`float`** **`long double`** значения или. В программе на языке C **remquo** всегда принимает два **`double`** аргумента и возвращает **`double`** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|--------------|---------------------|-|
|**remquo**, **ремкуоф**, **ремкуол**|\<math.h>|\<cmath> или \<math.h>|

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

## <a name="see-also"></a>См. также раздел

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
