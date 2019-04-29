---
title: exp, expf, expl
ms.date: 04/05/2018
apiname:
- expf
- expl
- exp
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
- _expl
- expf
- expl
- exp
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
ms.openlocfilehash: b9fb38adcc442e60864ec632cd92793f16e47502
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288192"
---
# <a name="exp-expf-expl"></a>exp, expf, expl

Вычисляет экспоненту.

## <a name="syntax"></a>Синтаксис

```C
double exp(
   double x
);
float exp(
   float x
);  // C++ only
long double exp(
   long double x
);  // C++ only
float expf(
   float x
);
long double expl(
   long double x
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
С плавающей запятой значение exponentiate натуральный логарифм по основанию *e* по.

## <a name="return-value"></a>Возвращаемое значение

**Exp** функции возвращают значение экспоненты параметра с плавающей запятой, *x*, при успешном выполнении. Результат является *e*<sup>*x*</sup>, где *e* является основанием натурального логарифма. В случае переполнения, функция возвращает INF (бесконечность), а также в случае переполнения **exp** возвращает 0.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± Несигнальное значение NaN, неопределенным|Нет|_DOMAIN|
|± Бесконечности|INVALID|_DOMAIN|
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|

**Exp** функция имеет реализацию, которая использует Streaming SIMD Extensions 2 (SSE2). Сведения о реализации SSE2 и ограничения на использование реализации SSE2 см. в разделе [_set_SSE2_enable](set-sse2-enable.md).

## <a name="remarks"></a>Примечания

C++ допускает перегрузку, поэтому можно вызывать перегрузки **exp** , принимающих **float** или **long double** аргумент. В программе на языке C **exp** всегда принимает и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок C|Обязательный заголовок C++|
|--------------|---------------------|---|
|**EXP**, **expf**, **новыми концепциями**|\<math.h>|\<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_exp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.302585093, y;

   y = exp( x );
   printf( "exp( %f ) = %f\n", x, y );
}
```

```Output
exp( 2.302585 ) = 10.000000
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
[_CIexp](../../c-runtime-library/ciexp.md)<br/>
