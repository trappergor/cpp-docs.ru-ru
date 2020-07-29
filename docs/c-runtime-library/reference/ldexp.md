---
title: ldexp, ldexpf, ldexpl
ms.date: 4/2/2020
api_name:
- ldexp
- ldexpf
- ldexpl
- _ldexpl
- _o_ldexp
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
- ldexp
- ldexpf
- ldexpl
- _ldexpl
helpviewer_keywords:
- calculating real numbers
- computing real numbers
- mantissas, floating-point variables
- ldexp function
- ldexpf function
- ldexpl function
- exponent, floating-point numbers
- floating-point functions, mantissa and exponent
ms.assetid: aa7f5310-3879-4f63-ae74-86a39fbdedfa
ms.openlocfilehash: bbd1742cdace30d5bc3bd5e9d592bb24a86f917f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216925"
---
# <a name="ldexp-ldexpf-ldexpl"></a>ldexp, ldexpf, ldexpl

Умножает число с плавающей запятой на целую степень числа два.

## <a name="syntax"></a>Синтаксис

```C
double ldexp(
   double x,
   int exp
);
float ldexp(
   float x,
   int exp
);  // C++ only
long double ldexp(
   long double x,
   int exp
);  // C++ only
float ldexpf(
   float x,
   int exp
);
long double ldexpl(
   long double x,
   int exp
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

*exp*<br/>
Целый показатель степени.

## <a name="return-value"></a>Возвращаемое значение

Функции **ldexp** возвращают значение EXP *x* \* 2 в<sup>*exp*</sup> случае успеха. В случае переполнения и, в зависимости от знака *x*, **ldexp** возвращает +/- **HUGE_VAL**; значение **errno** перестройки передается в **ERANGE**.

Дополнительные сведения о параметрах **возврата и** возможностях, возвращающих ошибки, см. в разделе "переводится [, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)".

## <a name="remarks"></a>Remarks

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **ldexp** , которые принимают **`float`** **`long double`** типы или. В программе на языке C **ldexp** всегда принимает **`double`** и, **`int`** и возвращает **`double`** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**ldexp**, **лдекспф**, **лдекспл**|\<math.h>|\<cmath>|

Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_ldexp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 4.0, y;
   int p = 3;

   y = ldexp( x, p );
   printf( "%2.1f times two to the power of %d is %2.1f\n", x, p, y );
}
```

## <a name="output"></a>Вывод

```Output
4.0 times two to the power of 3 is 32.0
```

## <a name="see-also"></a>См. также

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
