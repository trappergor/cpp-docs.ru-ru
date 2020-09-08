---
title: ldexp, ldexpf, ldexpl
description: Справочник по API для ldexp, лдекспф и лдекспл; что умножает число с плавающей запятой на целую степень числа двух.
ms.date: 9/1/2020
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
ms.openlocfilehash: 6ce6bcbc8adbc62e8d8598b97a6f77e04fee1511
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555453"
---
# <a name="ldexp-ldexpf-ldexpl"></a>ldexp, ldexpf, ldexpl

Умножает число с плавающей запятой на целую степень числа два.

## <a name="syntax"></a>Синтаксис

```C
double ldexp(
   double x,
   int exp
);
float ldexpf(
   float x,
   int exp
);
long double ldexpl(
   long double x,
   int exp
);
#define ldexp(X, INT) // Requires C11 or higher

float ldexp(
   float x,
   int exp
);  // C++ only
long double ldexp(
   long double x,
   int exp
);  // C++ only
```

### <a name="parameters"></a>Параметры

*x*\
Значение с плавающей запятой.

*расширением*\
Целый показатель степени.

## <a name="return-value"></a>Возвращаемое значение

Функции **ldexp** возвращают значение EXP *x* \* 2 в<sup>*exp*</sup> случае успеха. В случае переполнения и, в зависимости от знака *x*, **ldexp** возвращает +/- **HUGE_VAL**; значение **errno** перестройки передается в **ERANGE**.

Дополнительные сведения о параметрах **возврата и** возможностях, возвращающих ошибки, см. в разделе "переводится [, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)".

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **ldexp** , которые принимают **`float`** **`long double`** типы или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **ldexp** всегда принимает **`double`** и **`int`** и возвращает **`double`** .

При использовании \<tgmath.h> `ldexp()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**ldexp**, **лдекспф**, **лдекспл**|\<math.h>|\<cmath>|
|макрос **ldexp** | \<tgmath.h> ||

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
