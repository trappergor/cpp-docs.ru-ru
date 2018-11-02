---
title: frexp, frexpf, frexpl
ms.date: 04/05/2018
apiname:
- frexp
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
- frexp
- _frexpl
helpviewer_keywords:
- _frexpl function
- mantissas, floating-point variables
- frexpl function
- exponent, floating-point numbers
- frexp function
- floating-point functions, mantissa and exponent
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
ms.openlocfilehash: c9e259f730d2d63d07032735be930f6f0fdb17e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563846"
---
# <a name="frexp-frexpf-frexpl"></a>frexp, frexpf, frexpl

Возвращает мантиссу и степень числа с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double frexp(
   double x,
   int *expptr
);
float frexpf(
   float x,
   int * expptr
);
long double frexpl(
   long double x,
   int * expptr
);
float frexp(
   float x,
   int * expptr
);  // C++ only
long double frexp(
   long double x,
   int * expptr
);  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

*expptr*<br/>
Указатель на сохраненное значение целой части числа.

## <a name="return-value"></a>Возвращаемое значение

**frexp** возвращает мантиссы. Если *x* равно 0, функция возвращает значение 0 для мантиссы и экспоненты. Если *expptr* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает значение 0.

## <a name="remarks"></a>Примечания

**Frexp** функция разбивает значение с плавающей запятой (*x*) на мантиссу (*m*) и показатель степени (*n*), при котором абсолютное значение *m* больше или равно 0,5 и меньше 1,0, и *x* = *m* * 2<sup>*n*</sup>. Целый показатель степени *n* хранится в расположении, указанном *expptr*.

C++ допускает перегрузку, поэтому можно вызывать перегрузки **frexp**. В программе на языке C **frexp** всегда принимает **двойные** и **int** указатель и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**frexp**, **frexpf**, **frexpl**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_frexp.c
// This program calculates frexp( 16.4, &n )
// then displays y and n.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y;
   int n;

   x = 16.4;
   y = frexp( x, &n );
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );
}
```

```Output
frexp( 16.400000, &n ) = 0.512500, n = 5
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
