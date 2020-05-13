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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 38e79b547ad49c6f1c0f5a784d710838afdec388
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916797"
---
# <a name="pow-powf-powl"></a>pow, powf, powl

Вычисляет *x* , возведенное в степень *y*.

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

*&*<br/>
Экспонента.

## <a name="return-value"></a>Возвращаемое значение

Возвращает значение *x*<sup>*y*</sup>. Сообщение об ошибке не выводится в случае переполнения или потери значимости.

|Значения x и y|Возвращаемое значение функции pow|
|-----------------------|-------------------------|
|*x* ! = 0,0 и *y* = = 0,0|1|
|*x* = = 0,0 и *y* = = 0,0|1|
|*x* = = 0,0 и *y* < 0|INF|

## <a name="remarks"></a>Remarks

**Pow** не распознает целочисленные значения с плавающей запятой больше 2<sup>64</sup> (например, 1.0 E100).

**Pow** имеет реализацию, использующую Streaming SIMD Extensions 2 (SSE2). Сведения о реализации SSE2 и ограничениях на ее использование см. в разделе [_set_SSE2_enable](set-sse2-enable.md).

Поскольку C++ допускает перегрузку, можно вызвать любую из различных перегрузок **Pow**. В программе на языке C **Pow** всегда принимает два значения **типа Double** и возвращает значение **типа double** .

Перегрузка `pow(int, int)` более не доступна. При использовании этой перегрузки компилятор может выдать [C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md). Чтобы избежать этой проблемы, приведите первый параметр к типу **Double**, **float**или **Long** **Double**.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-|-|-|
|**Pow**, **powf**, **Повл**|\<math.h>|\<math.h> или \<cmath>|

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
