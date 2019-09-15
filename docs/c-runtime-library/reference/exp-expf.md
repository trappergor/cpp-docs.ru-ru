---
title: exp, expf, expl
ms.date: 04/05/2018
api_name:
- expf
- expl
- exp
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 380f3e861b3ae1ba2f57aa781c32829771612b9f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941637"
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
Значение с плавающей запятой, експонентиате основание натурального логарифма по адресу *e* .

## <a name="return-value"></a>Возвращаемое значение

Функции **exp** возвращают экспоненциальное значение параметра с плавающей запятой *x*, если выполнено успешно. То есть результатом является *e*<sup>*x*</sup>, где *e* — основание натурального логарифма. При переполнении функция возвращает INF-файл (бесконечность) и при неточном потоке **exp** возвращает 0.

|Ввод|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± Скрытого NaN, неопределенного|Отсутствуют|_DOMAIN|
|± Бесконечности|INVALID|_DOMAIN|
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|

Функция **exp** имеет реализацию, использующую Streaming SIMD Extensions 2 (SSE2). Сведения о реализации SSE2 и ограничения на использование реализации SSE2 см. в разделе [_set_SSE2_enable](set-sse2-enable.md).

## <a name="remarks"></a>Примечания

C++допускает перегрузку, поэтому можно вызывать перегрузки **exp** , принимающие аргумент с **плавающей запятой** или **Long** . В программе C **exp** всегда принимает и возвращает значение **типа Double**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок C|Обязательный заголовок C++|
|--------------|---------------------|---|
|**exp**, **експф**, **експл**|\<math.h>|\<cmath> или \<math.h>|

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
