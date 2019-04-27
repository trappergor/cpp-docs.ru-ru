---
title: modf, modff, modfl
ms.date: 04/05/2018
apiname:
- modff
- modf
- modfl
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
ms.openlocfilehash: 59d6e2b9b02ad182c5630d6dc9a989c035e8fa92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156334"
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

*intptr*<br/>
Указатель на сохраненное значение целой части числа.

## <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает дробную часть числа *x* со знаком. Ошибка не возвращается.

## <a name="remarks"></a>Примечания

**Modf** функции разбить значение с плавающей запятой *x* на дробную и целую части, каждая из которых имеет тот же знак, что *x*. Со знаком дробной части числа *x* возвращается. Целая часть сохраняется как значение с плавающей запятой в *intptr*.

**modf** имеет реализацию, которая использует Streaming SIMD Extensions 2 (SSE2). Сведения о реализации SSE2 и ограничения на использование реализации SSE2 см. в разделе [_set_SSE2_enable](set-sse2-enable.md).

C++ допускает перегрузку, поэтому можно вызывать перегрузки **modf** , принимающие и возвращающие **float** или **long** **двойные** параметров. В программе на языке C **modf** всегда принимает два значения типа double и возвращает значение типа double.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**modf**, **modff**, **modfl**|C: \<math.h><br /><br /> C++: , \<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
