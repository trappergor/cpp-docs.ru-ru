---
title: asinh, asinhf, asinhl
description: Справочник по API для ASINH, асинхф и асинхл; который вычисляет обратный гиперболический синус значения с плавающей запятой.
ms.date: 08/31/2020
api_name:
- asinh
- asinhf
- asinhl
- _o_asinh
- _o_asinhf
- _o_asinhl
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
- asinhf
- asinhl
- asinh
helpviewer_keywords:
- asinh function
- asinhl function
- asinhf function
ms.assetid: 4488babe-1a7e-44ca-8b7b-c2db0a70084f
ms.openlocfilehash: face2eb5f7c6220e1a4369ae0aa11514a918d21c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91505606"
---
# <a name="asinh-asinhf-asinhl"></a>asinh, asinhf, asinhl

Вычисляет обратный гиперболический синус.

## <a name="syntax"></a>Синтаксис

```C
double asinh( double x );
float asinhf( float x );
long double asinhl( long double x );
#define asinh(X) // Requires C11 or higher

float asinh( float x );  // C++ only
long double asinh( long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **ASINH** возвращают обратный гиперболический синус (дугу гиперболического синуса) *x*. Эта функция допустима для домена чисел с плавающей запятой. Если *x* является недействительным неопределенным или бесконечностью, то возвращается одно и то же значение.

|Входные данные|Исключение SEH|**_matherr** Об|
|-----------|-------------------|--------------------------|
|± КНАН, ТО ЖЕ, INF|нет|нет|

## <a name="remarks"></a>Remarks

При использовании C++ можно вызывать перегрузки **ASINH** , которые принимают и возвращают **`float`** **`long double`** значения или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **ASINH** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `asinh()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок C|Обязательный заголовок C++|
|--------------|--------------|------------------|
|**ASINH**, **асинхф**, **асинхл**|\<math.h>|\<cmath> либо \<math.h>|
|макрос **Asinh ()** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_asinh.c
// Compile by using: cl /W4 crt_asinh.c
// This program displays the hyperbolic sine of pi / 4
// and the arc hyperbolic sine of the result.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = sinh( pi / 4 );
   y = asinh( x );
   printf( "sinh( %f ) = %f\n", pi/4, x );
   printf( "asinh( %f ) = %f\n", x, y );
}
```

```Output
sinh( 0.785398 ) = 0.868671
asinh( 0.868671 ) = 0.785398
```

## <a name="see-also"></a>См. также раздел

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
