---
title: pow, powf, powl
ms.date: 4/2/2020
api_name:
- powl
- pow
- powf
- _o_pow
- _o_powf
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
- powl
- pow
- _powl
- powf
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
ms.openlocfilehash: b181959ac05814a673ab11f33e4cfc5a39e3869e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333119"
---
# <a name="pow-powf-powl"></a>pow, powf, powl

Вычисляет *x* поднятые к силе *y*.

## <a name="syntax"></a>Синтаксис

```C
double pow( double x, double y );
float powf( float x, float y );
long double powl( long double x, long double y );
```

```cpp
double pow( double x, int y );  // C++ only
float pow( float x, float y );  // C++ only
float pow( float x, int y );  // C++ only
long double pow( long double x, long double y );  // C++ only
long double pow( long double x, int y );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
База.

*Y*<br/>
Экспонента.

## <a name="return-value"></a>Возвращаемое значение

Возвращает значение *x*<sup>*y*</sup>. Сообщение об ошибке не выводится в случае переполнения или потери значимости.

|Значения x и y|Возвращаемое значение функции pow|
|-----------------------|-------------------------|
|*x* ! » 0,0 и *y* q 0.0|1|
|*х* 0,0 и *0,0*|1|
|*х* 0,0 *и* у < 0|INF|

## <a name="remarks"></a>Remarks

**pow** не распознает значения интегральных плавающих точек, превышающие 2<sup>64</sup> (например, 1.0E100).

**pow** имеет реализацию, которая использует потоковое SIMD расширения 2 (SSE2). Сведения о реализации SSE2 и ограничениях на ее использование см. в разделе [_set_SSE2_enable](set-sse2-enable.md).

Так как СЗ позволяет перегружать, вы можете вызвать любую из различных перегрузок **пау.** В программе **C, pow** всегда принимает 2 **двойных** значения и возвращает **двойное** значение.

Перегрузка `pow(int, int)` более не доступна. Если вы используете эту перегрузку, компилятор может излучать [C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md). Чтобы избежать этой проблемы, бросить первый параметр в **два раза,** **плавать,** или **долго** **двойной**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-|-|-|
|**пау**, **powf**, **powl**|\<math.h>|\<math.h> или \<cmath>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_pow.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.0, y = 3.0, z;

   z = pow( x, y );
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );
}
```

```Output
2.0 to the power of 3.0 is 8.0
```

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md) <br/>
[exp, expf, expl](exp-expf.md) <br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md) <br/>
[sqrt, sqrtf, sqrtl](sqrt-sqrtf-sqrtl.md) <br/>
[_CIpow](../../c-runtime-library/cipow.md)<br/>
