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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 644e50564f1b433921a6a0d8099ea5229db7ed93
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216873"
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

*Дескриптор*<br/>
Указатель на сохраненное значение целой части числа.

## <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает дробную часть числа *x* со знаком. Ошибка не возвращается.

## <a name="remarks"></a>Remarks

Функции **modf** разбивают значение *x* с плавающей запятой на дробные и целые части, каждый из которых имеет тот же знак, что и *x*. Возвращается знак дробной части *x* . Целая часть сохраняется как значение с плавающей запятой в *IntPtr*.

**modf** имеет реализацию, использующую Streaming SIMD Extensions 2 (SSE2). Сведения о реализации SSE2 и ограничения на использование реализации SSE2 см. в разделе [_set_SSE2_enable](set-sse2-enable.md).

C++ допускает перегрузку, поэтому можно вызывать перегрузки **modf** , которые принимают и возвращают **`float`** **`long double`** Параметры или. В программе на языке C **modf** всегда принимает два значения типа Double и возвращает значение типа Double.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**modf**, **modff**, **модфл**|Ц\<math.h><br /><br /> C++: \<cmath> или\<math.h>|

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

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
