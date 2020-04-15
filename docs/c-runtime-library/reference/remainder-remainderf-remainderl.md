---
title: remainder, remainderf, remainderl
ms.date: 4/2/2020
api_name:
- remainderl
- remainder
- remainderf
- _o_remainder
- _o_remainderf
- _o_remainderl
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- remainderf
- remainder
- remainderl
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
ms.openlocfilehash: 4b70d3175a125d72ff67710c83899c44dbf72015
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332864"
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

Вычисляет остаток от частного двух чисел с плавающей запятой, округленного до ближайшего целого значения.

## <a name="syntax"></a>Синтаксис

```C
double remainder( double x, double y );
float remainderf( float x, float y );
long double remainderl( long double x, long double y );
```

```cpp
float remainder( float x, float y ); /* C++ only */
long double remainder( long double x, long double y ); /* C++ only */
```

### <a name="parameters"></a>Параметры

*x*<br/>
Числитель.

*Y*<br/>
Знаменатель.

## <a name="return-value"></a>Возвращаемое значение

Остаток плавающей точки *x* / *y*. Если значение *y* 0.0, **остаток** возвращает тихий NaN. Для получения информации о представлении тихого NaN семьи **printf,** [см. printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Remarks

**Остальные** функции вычислить плавающей точки остатка *r* *х* / *у* так, что *х* = *n* \* *у* + *р*, где *n*является целью ближайший по значению *х* / *у* и *n*даже тогда, когда &#124; *n* - *х* / *у* &#124; 1'2. Когда *r* q 0, *r* имеет такой же знак как *x*.

Поскольку СЗ допускает перегрузку, можно вызывать перегрузки **остатков,** которые принимают и возвращают **плавающие** или **длинные** **двойные** значения. В программе **C, остаток** всегда принимает два **двойных** аргумента и возвращает **двойной**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|--------------|---------------------|-|
|**остаток**, **remainderf**, **remainderl**|\<math.h>|\<cmath> или \<math.h>|

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

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
