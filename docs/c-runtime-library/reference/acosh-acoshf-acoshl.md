---
title: acosh, acoshf, acoshl
description: Справочник по API для ACOSH, acoshf и акошл; который вычисляет обратный гиперболический косинус значения с плавающей запятой.
ms.date: 08/31/2020
api_name:
- acoshf
- acosh
- acoshl
- _o_acosh
- _o_acoshf
- _o_acoshl
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
- acosh
- acoshf
- acoshl
- math/acosh
- math/acoshf
- math/acoshl
helpviewer_keywords:
- acoshf function
- acosh function
- acoshl function
ms.assetid: 6985c4d7-9e2a-44ce-9a9b-5a43015f15f7
ms.openlocfilehash: ef6d47ca07f96be84962303c13162b154086e5f2
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555115"
---
# <a name="acosh-acoshf-acoshl"></a>acosh, acoshf, acoshl

Вычисляет обратный гиперболический косинус.

## <a name="syntax"></a>Синтаксис

```C
double acosh( double x );
float acoshf( float x );
long double acoshl( long double x );
#define acosh(X) // Requires C11 or higher

float acosh( float x );  // C++ only
long double acosh( long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*\
Значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **ACOSH** возвращают обратный гиперболический-косинус (Дуга гиперболического косинуса) *x*. Эти функции действительны для домена *x* ≥ 1. Если значение *x* меньше 1, то устанавливается `errno` в, `EDOM` а результатом является скрытое значение NaN. Если *x* является недействительным неопределенным или бесконечностью, то возвращается одно и то же значение.

|Входные данные|Исключение SEH|Исключение`_matherr`|
|-----------|-------------------|--------------------------|
|± КНАН, ТО ЖЕ, INF|нет|нет|
|*x* < 1|нет|нет|

## <a name="remarks"></a>Примечания

При использовании C++ можно вызывать перегрузки **ACOSH** , которые принимают и возвращают **`float`** **`long double`** значения или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **ACOSH** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `acosh()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**ACOSH**, **acoshf**, **акошл**|\<math.h>|\<cmath>|
|макрос **ACOSH ()** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_acosh.c
// Compile by using: cl /W4 crt_acosh.c
// This program displays the hyperbolic cosine of pi / 4
// and the arc hyperbolic cosine of the result.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = cosh( pi / 4 );
   y = acosh( x );
   printf( "cosh( %f ) = %f\n", pi/4, x );
   printf( "acosh( %f ) = %f\n", x, y );
}
```

```Output
cosh( 0.785398 ) = 1.324609
acosh( 1.324609 ) = 0.785398
```

## <a name="see-also"></a>См. также

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)
