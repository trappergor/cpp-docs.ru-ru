---
title: modf, modff, modfl
ms.date: 4/2/2020
api_name:
- modff
- modf
- modfl
- _o_modf
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
ms.openlocfilehash: b509da5f18ea1f606b8a3b47ab66a78e4f595558
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338686"
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl

Разбивает значение с плавающей запятой на дробную и целую части.

## <a name="syntax"></a>Синтаксис

```C
double modf( double x, double * intptr );
float modff( float x, float * intptr );
long double modfl( long double x, long double * intptr );
```

```cpp
float modf( float x, float * intptr );  // C++ only
long double modf( long double x, long double * intptr );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

*Intptr*<br/>
Указатель на сохраненное значение целой части числа.

## <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает дробную часть числа *x* со знаком. Ошибка не возвращается.

## <a name="remarks"></a>Remarks

Функции **модфа** разбивают значение плавающей точки *x* на дробные и целые части, каждая из которых имеет тот же знак, что и *x.* Подписанная дробная часть *x* возвращается. Целый ряд хранится в виде значения плавающей точки в *intptr.*

**modf** имеет реализацию, которая использует потоковое SIMD расширения 2 (SSE2). Сведения о реализации SSE2 и ограничения на использование реализации SSE2 см. в разделе [_set_SSE2_enable](set-sse2-enable.md).

СЗ позволяет перегружать, так что вы можете вызвать перегрузки **modf,** которые принимают и возвращают **поплавок** или **длинные** **двойные** параметры. В программе C **modf** всегда имеет два двойных значения и возвращает двойное значение.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**modf**, **modff**, **modfl**|C: \<math.h><br /><br /> C++: , \<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
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

```Output
For -14.876543, the fraction is -0.876543 and the integer is -14
```

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
