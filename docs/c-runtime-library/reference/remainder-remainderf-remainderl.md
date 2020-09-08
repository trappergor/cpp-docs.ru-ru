---
title: remainder, remainderf, remainderl
description: Справочник по API для оставшейся части, ремаиндерф и остатка; который вычислит остаток от деления двух значений с плавающей запятой, округленных до ближайшего целого значения.
ms.date: 9/1/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: ef2b326bef2288b52dba8988749e030ff0b46077
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556013"
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

Вычисляет остаток от частного двух чисел с плавающей запятой, округленного до ближайшего целого значения.

## <a name="syntax"></a>Синтаксис

```C
double remainder( double x, double y );
float remainderf( float x, float y );
long double remainderl( long double x, long double y );
#define remainder(X, Y) // Requires C11 or higher

float remainder( float x, float y ); /* C++ only */
long double remainder( long double x, long double y ); /* C++ only */
```

### <a name="parameters"></a>Параметры

*x*\
Числитель.

*&*\
Знаменатель.

## <a name="return-value"></a>Возвращаемое значение

Остаток от деления *x*y на число с плавающей запятой  /  *y*. Если значение *y* равно 0,0, то функция **остаток** возвращает нетихом NaN. Сведения о представлении нескрытого числа NaN в семействе **printf** см. в разделе [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Примечания

Функции **остатка** вычисляют значение *x*y *остатка* с плавающей запятой  /  *y* таким, что *x*  =  *n* \* *y*  +  *r*, где *n*— целое число, ближайшее к значению *x*  /  *y* , а *n*— даже каждый раз, когда &#124; *n*  -  *x*  /  *y* &#124; = 1/2. Если *r* = 0, *r* имеет тот же знак, что и *x*.

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **остатка** , которые принимают и возвращают **`float`** **`long double`** значения или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, функция **остаток** всегда принимает два **`double`** аргумента и возвращает **`double`** .

При использовании \<tgmath.h> `remainder()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|--------------|---------------------|-|
|**остаток**, **ремаиндерф**, **остаток**|\<math.h>|\<cmath> или \<math.h>|
|макрос **остатка** | \<tgmath.h> ||

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

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)\
[ldiv, lldiv](ldiv-lldiv.md)\
[imaxdiv](imaxdiv.md)\
[FMOD, фмодф](fmod-fmodf.md)\
[remquo, remquof, remquol](remquo-remquof-remquol.md)
