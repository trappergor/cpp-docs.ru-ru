---
title: asinh, asinhf, asinhl
ms.date: 04/05/2018
api_name:
- asinh
- asinhf
- asinhl
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
- asinhf
- asinhl
- asinh
helpviewer_keywords:
- asinh function
- asinhl function
- asinhf function
ms.assetid: 4488babe-1a7e-44ca-8b7b-c2db0a70084f
ms.openlocfilehash: f4d93f121c0124293a5bdff9041d0adfaab5d83c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939643"
---
# <a name="asinh-asinhf-asinhl"></a>asinh, asinhf, asinhl

Вычисляет обратный гиперболический синус.

## <a name="syntax"></a>Синтаксис

```C
double asinh( double x );
float asinhf( float x );
long double asinhl( long double x );
```

```cpp
float asinh( float x );  // C++ only
long double asinh( long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **ASINH** возвращают обратный гиперболический синус (дугу гиперболического синуса) *x*. Эта функция допустима для домена чисел с плавающей запятой. Если *x* является недействительным неопределенным или бесконечностью, то возвращается одно и то же значение.

|Ввод|Исключение SEH|**_matherr** Об|
|-----------|-------------------|--------------------------|
|± КНАН, ТО ЖЕ, INF|none|none|

## <a name="remarks"></a>Примечания

C++При использовании можно вызывать перегрузки **ASINH** , которые принимают и возвращают значения **типа float** или **Long** . В программе на языке C **ASINH** всегда принимает и возвращает **Double**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок C|Обязательный заголовок C++|
|--------------|--------------|------------------|
|**ASINH**, **асинхф**, **асинхл**|\<math.h>|\<cmath > или \<Math. h <|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
