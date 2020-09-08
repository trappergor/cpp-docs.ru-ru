---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
description: Справочник по API для nextafter, некстафтерф, некстафтерл, _nextafter, _nextafterf, нексттовард, нексттовардф и нексттовардл; который возвращает следующее представимое значение с плавающей точкой.
ms.date: 9/1/2020
api_name:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
- _o__nextafter
- _o_nextafter
- _o_nextafterf
- _o_nextafterl
- _o_nexttoward
- _o_nexttowardf
- _o_nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
ms.openlocfilehash: cdcfb1a1d0bf1523a0252d779dba603ce1814b14
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555830"
---
# <a name="nextafter-nextafterf-nextafterl-_nextafter-_nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

Возвращает следующее представимое значение с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

#define nextafter(X, Y) // Requires C11 or higher

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );

#define nexttoward(X, Y) // Requires C11 or higher

float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>Параметры

*x*\
Начальное значение с плавающей запятой.

*&*\
Следующее значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Возвращает следующее представимое значение с плавающей запятой возвращаемого типа после *x* в направлении *y*. Если *x* и *y* равны, функция возвращает *y*, преобразованную в тип возвращаемого значения, без исключения. Если значение *x* не равно *y*, а результат является нормальным или нулевым, то задаются **FE_UNDERFLOW** и **FE_INEXACT** состояния исключений с плавающей запятой, и возвращается правильный результат. Если либо *x* , либо *y* является NaN, то возвращаемое значение является одним из входных значений NaN. Если *x* является конечным, а результат является бесконечным или недоступным для представления в типе, возвращается правильно подписанная бесконечность или NAN, **FE_OVERFLOW** и **FE_INEXACT** состояния исключений с плавающей запятой задаются, а параметру " **переводится** " значение **ERANGE**.

## <a name="remarks"></a>Примечания

Семейства функций **nextafter** и **нексттовард** эквивалентны, за исключением типа параметра *y*. Если *x* и *y* равны, возвращается значение *y* , преобразованное в тип возвращаемого значения.

Так как C++ допускает перегрузку, при включении \<cmath> можно вызывать перегрузки **nextafter** и **нексттовард** , которые возвращают **`float`** **`long double`** типы и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **nextafter** и **нексттовард** всегда возвращают **`double`** .

При использовании \<tgmath.h> `nextafter()` `nexttoward()` макроса или тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

Функции **_nextafter** и **_nextafterf** являются специфичными для Microsoft. Функция **_nextafterf** доступна только при компиляции для x64.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **некстафтерф**, **некстафтерл**, **_nextafterf**, **нексттовард**, **нексттовардф**, **нексттовардл**|\<math.h>|\<math.h> или \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> или \<cfloat>|
|макрос **nextafter** , макрос **нексттовард**| \<tgmath.h> ||

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)\
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)
