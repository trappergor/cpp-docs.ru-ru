---
title: Функции пространства имен Concurrency::precise_math
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::precise_math::acos
- amp_math/Concurrency::precise_math::acosh
- amp_math/Concurrency::precise_math::acoshf
- amp_math/Concurrency::precise_math::asinf
- amp_math/Concurrency::precise_math::asinh
- amp_math/Concurrency::precise_math::atan
- amp_math/Concurrency::precise_math::atan2
- amp_math/Concurrency::precise_math::atanf
- amp_math/Concurrency::precise_math::atanh
- amp_math/Concurrency::precise_math::cbrt
- amp_math/Concurrency::precise_math::cbrtf
- amp_math/Concurrency::precise_math::ceilf
- amp_math/Concurrency::precise_math::copysign
- amp_math/Concurrency::precise_math::cos
- amp_math/Concurrency::precise_math::cosf
- amp_math/Concurrency::precise_math::coshf
- amp_math/Concurrency::precise_math::cospi
- amp_math/Concurrency::precise_math::erf
- amp_math/Concurrency::precise_math::erfc
- amp_math/Concurrency::precise_math::erfcinv
- amp_math/Concurrency::precise_math::erfcinvf
- amp_math/Concurrency::precise_math::erfinv
- amp_math/Concurrency::precise_math::erfinvf
- amp_math/Concurrency::precise_math::exp10
- amp_math/Concurrency::precise_math::exp10f
- amp_math/Concurrency::precise_math::exp2f
- amp_math/Concurrency::precise_math::expf
- amp_math/Concurrency::precise_math::expm1f
- amp_math/Concurrency::precise_math::fabs
- amp_math/Concurrency::precise_math::floor
- amp_math/Concurrency::precise_math::fdim
- amp_math/Concurrency::precise_math::floorf
- amp_math/Concurrency::precise_math::fmaf
- amp_math/Concurrency::precise_math::fmaxf
- amp_math/Concurrency::precise_math::fmin
- amp_math/Concurrency::precise_math::fmod
- amp_math/Concurrency::precise_math::fmodf
- amp_math/Concurrency::precise_math::frexp
- amp_math/Concurrency::precise_math::frexpf
- amp_math/Concurrency::precise_math::hypotf
- amp_math/Concurrency::precise_math::ilogb
- amp_math/Concurrency::precise_math::isfinite
- amp_math/Concurrency::precise_math::isinf
- amp_math/Concurrency::precise_math::isnormal
- amp_math/Concurrency::precise_math::ldexp
- amp_math/Concurrency::precise_math::lgamma
- amp_math/Concurrency::precise_math::lgammaf
- amp_math/Concurrency::precise_math::log10
- amp_math/Concurrency::precise_math::log10f
- amp_math/Concurrency::precise_math::log1pf
- amp_math/Concurrency::precise_math::log2
- amp_math/Concurrency::precise_math::logb
- amp_math/Concurrency::precise_math::logbf
- amp_math/Concurrency::precise_math::modf
- amp_math/Concurrency::precise_math::modff
- amp_math/Concurrency::precise_math::nanf
- amp_math/Concurrency::precise_math::nearbyint
- amp_math/Concurrency::precise_math::nextafter
- amp_math/Concurrency::precise_math::nextafterf
- amp_math/Concurrency::precise_math::phif
- amp_math/Concurrency::precise_math::pow
- amp_math/Concurrency::precise_math::probit
- amp_math/Concurrency::precise_math::probitf
- amp_math/Concurrency::precise_math::rcbrtf
- amp_math/Concurrency::precise_math::remainder
- amp_math/Concurrency::precise_math::remquo
- amp_math/Concurrency::precise_math::remquof
- amp_math/Concurrency::precise_math::roundf
- amp_math/Concurrency::precise_math::rsqrt
- amp_math/Concurrency::precise_math::scalb
- amp_math/Concurrency::precise_math::scalbf
- amp_math/Concurrency::precise_math::scalbnf
- amp_math/Concurrency::precise_math::signbit
- amp_math/Concurrency::precise_math::sin
- amp_math/Concurrency::precise_math::sincos
- amp_math/Concurrency::precise_math::sinf
- amp_math/Concurrency::precise_math::sinh
- amp_math/Concurrency::precise_math::sinpi
- amp_math/Concurrency::precise_math::sinpif
- amp_math/Concurrency::precise_math::sqrtf
- amp_math/Concurrency::precise_math::tan
- amp_math/Concurrency::precise_math::tanh
- amp_math/Concurrency::precise_math::tanhf
- amp_math/Concurrency::precise_math::tanpif
- amp_math/Concurrency::precise_math::tgamma
- amp_math/Concurrency::precise_math::trunc
- amp_math/Concurrency::precise_math::truncf
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
ms.openlocfilehash: ee6ab2313fbdc288ebba1b3fdacf192b7b578eb6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321855"
---
# <a name="concurrencyprecise_math-namespace-functions"></a>Функции пространства имен Concurrency::precise_math

||||
|-|-|-|
|[акос](#acos)|[acosf](#acosf)|[acosh](#acosh)|
|[acoshf](#acoshf)|[Asin](#asin)|[asinf](#asinf)|
|[asinh](#asinh)|[asinhf](#asinhf)|[Atan](#atan)|
|[atan2](#atan2)|[atan2f](#atan2f)|[atanf](#atanf)|
|[atanh](#atanh)|[atanhf](#atanhf)|[cbrt](#cbrt)|
|[cbrtf](#cbrtf)|[ceil](#ceil)|[ceilf](#ceilf)|
|[копилк](#copysign)|[copysignf](#copysignf)|[Потому что](#cos)|
|[cosf](#cosf)|[cosh](#cosh)|[coshf](#coshf)|
|[cospi](#cospi)|[коспиф](#cospif)|[erf](#erf)|
|[erfc](#erfc)|[erfcf](#erfcf)|[erfcinv](#erfcinv)|
|[erfcinvf](#erfcinvf)|[erff](#erff)|[erfinv](#erfinv)|
|[erfinvf](#erfinvf)|[Exp](#exp)|[exp10](#exp10)|
|[exp10f](#exp10f)|[exp2](#exp2)|[exp2f](#exp2f)|
|[expf](#expf)|[expm1](#expm1)|[expm1f](#expm1f)|
|[fabs](#fabs)|[fabsf](#fabsf)|[Этаже](#floor)|
|[fdim](#fdim)|[fdimf](#fdimf)||
|[floorf](#floorf)|[fma](#fma)|[fmaf](#fmaf)|
[fmax](#fmax)|[fmaxf](#fmaxf)||
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|
|[fmodf](#fmodf)|[fpclassify](#fpclassify)|[frexp](#frexp)|
|[frexpf](#frexpf)|[hypot](#hypot)|[hypotf](#hypotf)|
|[ilogb](#ilogb)|[ilogbf](#ilogbf)|[исфинит](#isfinite)|
|[isinf](#isinf)|[isnan](#isnan)|[isnormal](#isnormal)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[lgamma](#lgamma)|
|[lgammaf](#lgammaf)|[Журнала](#log)|[log10](#log10)|
|[log10f](#log10f)|[log1p](#log1p)|[log1pf](#log1pf)|
|[log2](#log2)|[log2f](#log2f)|[logb](#logb)|
|[logbf](#logbf)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[не число](#nan)|[nanf](#nanf)|
|[nearbyint](#nearbyint)|[nearbyintf](#nearbyintf)|[в следующий раз](#nextafter)|
|[nextafterf](#nextafterf)|[Phi](#phi)|[phif](#phif)|
|[pow](#pow)|[powf](#powf)|[пробит](#probit)|
|[probitf](#probitf)|[rcbrt](#rcbrt)|[rcbrtf](#rcbrtf)|
|[remainder](#remainder)|[remainderf](#remainderf)|[remquo](#remquo)|
|[remquof](#remquof)|[Круглый](#round)|[roundf](#roundf)|
|[rsqrt](#rsqrt)|[rsqrtf](#rsqrtf)|[scalb](#scalb)|
|[scalbf](#scalbf)|[scalbn](#scalbn)|[scalbnf](#scalbnf)|
|[signbit](#signbit)|[signbitf](#signbitf)|[Грех](#sin)|
|[синкосы](#sincos)|[sincosf](#sincosf)|[sinf](#sinf)|
|[sinh](#sinh)|[sinhf](#sinhf)|[синпи](#sinpi)|
|[синпиф](#sinpif)|[Sqrt](#sqrt)|[sqrtf](#sqrtf)|
|[Загар](#tan)|[tanf](#tanf)|[тан](#tanh)|
|[tanhf](#tanhf)|[танпи](#tanpi)|[танпиф](#tanpif)|
|[tgamma](#tgamma)|[tgammaf](#tgammaf)|[Trunc](#trunc)|
|[truncf](#truncf)|

## <a name="acos"></a><a name="acos"></a>акос

Вычисляет арккосин аргумента

```cpp
inline float acos(float _X) restrict(amp);

inline double acos(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арккозина аргумента

## <a name="acosf"></a><a name="acosf"></a>acosf

Вычисляет арккосин аргумента

```cpp
inline float acosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арккозина аргумента

## <a name="acosh"></a><a name="acosh"></a>акош

Вычисляет обратный гиперболический косин аргумента

```cpp
inline float acosh(float _X) restrict(amp);

inline double acosh(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратное гиперболическое косиновское значение аргумента

## <a name="acoshf"></a><a name="acoshf"></a>акошф

Вычисляет обратный гиперболический косин аргумента

```cpp
inline float acoshf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратное гиперболическое косиновское значение аргумента

## <a name="asin"></a><a name="asin"></a>Asin

Вычисляет дуги аргумента

```cpp
inline float asin(float _X) restrict(amp);

inline double asin(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение дуги аргумента

## <a name="asinf"></a><a name="asinf"></a>asinf

Вычисляет дуги аргумента

```cpp
inline float asinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение дуги аргумента

## <a name="asinh"></a><a name="asinh"></a>асин

Вычисляет обратную гиперболическую синусоигу аргумента

```cpp
inline float asinh(float _X) restrict(amp);

inline double asinh(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную гиперболическую синусоидную ценность аргумента

## <a name="asinhf"></a><a name="asinhf"></a>asinhf

Вычисляет обратную гиперболическую синусоигу аргумента

```cpp
inline float asinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную гиперболическую синусоидную ценность аргумента

## <a name="atan"></a><a name="atan"></a>Atan

Вычисляет арктангенс аргумента.

```cpp
inline float atan(float _X) restrict(amp);

inline double atan(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает arctangent значение аргумента

## <a name="atan2"></a><a name="atan2"></a>atan2

Вычисляет дугтанген _Y/_X

```cpp
inline float atan2(
    float _Y,
    float _X) restrict(amp);

inline double atan2(
    double _Y,
    double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_y*<br/>
Значение с плавающей запятой

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение arctangent _Y/_X

## <a name="atan2f"></a><a name="atan2f"></a>atan2f

Вычисляет дугтанген _Y/_X

```cpp
inline float atan2f(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_y*<br/>
Значение с плавающей запятой

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение arctangent _Y/_X

## <a name="atanf"></a><a name="atanf"></a>атанф

Вычисляет арктангенс аргумента.

```cpp
inline float atanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает arctangent значение аргумента

## <a name="atanh"></a><a name="atanh"></a>атанх

Вычисляет обратную гиперболическую касательную аргумента

```cpp
inline float atanh(float _X) restrict(amp);

inline double atanh(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратное гиперболическое касательное значение аргумента

## <a name="atanhf"></a><a name="atanhf"></a>атанхф

Вычисляет обратную гиперболическую касательную аргумента

```cpp
inline float atanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратное гиперболическое касательное значение аргумента

## <a name="cbrt"></a><a name="cbrt"></a>cbrt

Вычисляет реальный корень куба аргумента

```cpp
inline float cbrt(float _X) restrict(amp);

inline double cbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает реальный корень куба аргумента

## <a name="cbrtf"></a><a name="cbrtf"></a>cbrtf

Вычисляет реальный корень куба аргумента

```cpp
inline float cbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает реальный корень куба аргумента

## <a name="ceil"></a><a name="ceil"></a>ceil

Высчитывает потолок аргумента

```cpp
inline float ceil(float _X) restrict(amp);

inline double ceil(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает потолок аргумента

## <a name="ceilf"></a><a name="ceilf"></a>цейльф

Высчитывает потолок аргумента

```cpp
inline float ceilf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает потолок аргумента

## <a name="copysign"></a><a name="copysign"></a>копилк

Производит значение с величиной _X и признаком _Y

```cpp
inline float copysign(
    float _X,
    float _Y) restrict(amp);

inline double copysign(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение с величиной _X и признаком _Y

## <a name="copysignf"></a><a name="copysignf"></a>копий

Производит значение с величиной _X и признаком _Y

```cpp
inline float copysignf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение с величиной _X и признаком _Y

## <a name="cos"></a><a name="cos"></a>Потому что

Вычисляет косинус аргумента.

```cpp
inline float cos(float _X) restrict(amp);

inline double cos(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает косиное значение аргумента

## <a name="cosf"></a><a name="cosf"></a>Cosf

Вычисляет косинус аргумента.

```cpp
inline float cosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает косиное значение аргумента

## <a name="cosh"></a><a name="cosh"></a>Cosh

Рассчитывает гиперболическую косиновую ценность аргумента

```cpp
inline float cosh(float _X) restrict(amp);

inline double cosh(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает гиперболическую косиновую ценность аргумента

## <a name="coshf"></a><a name="coshf"></a>coshf

Рассчитывает гиперболическую косиновую ценность аргумента

```cpp
inline float coshf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает гиперболическую косиновую ценность аргумента

## <a name="cospi"></a><a name="cospi"></a>cospi

Рассчитывает косиное значение пи \* _X

```cpp
inline float cospi(float _X) restrict(amp);

inline double cospi(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает косиновый значение \* пи _X

## <a name="cospif"></a><a name="cospif"></a>коспиф

Рассчитывает косиное значение пи \* _X

```cpp
inline float cospif(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает косиновый значение \* пи _X

## <a name="erf"></a><a name="erf"></a>Erf

Вычисляет функцию ошибки _X

```cpp
inline float erf(float _X) restrict(amp);

inline double erf(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает функцию ошибки _X

## <a name="erfc"></a><a name="erfc"></a>erfc

Вычисляет функцию дополнительной ошибки _X

```cpp
inline float erfc(float _X) restrict(amp);

inline double erfc(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает функцию дополнительной ошибки _X

## <a name="erfcf"></a><a name="erfcf"></a>erfcf

Вычисляет функцию дополнительной ошибки _X

```cpp
inline float erfcf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает функцию дополнительной ошибки _X

## <a name="erfcinv"></a><a name="erfcinv"></a>erfcinv

Вычисляет обратную функцию дополнительной ошибки _X

```cpp
inline float erfcinv(float _X) restrict(amp);

inline double erfcinv(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную функцию дополнительной ошибки _X

## <a name="erfcinvf"></a><a name="erfcinvf"></a>erfcinvf

Вычисляет обратную функцию дополнительной ошибки _X

```cpp
inline float erfcinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную функцию дополнительной ошибки _X

## <a name="erff"></a><a name="erff"></a>erff

Вычисляет функцию ошибки _X

```cpp
inline float erff(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает функцию ошибки _X

## <a name="erfinv"></a><a name="erfinv"></a>erfinv

Вычисляет обратную функцию ошибки _X

```cpp
inline float erfinv(float _X) restrict(amp);

inline double erfinv(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную функцию ошибки _X

## <a name="erfinvf"></a><a name="erfinvf"></a>erfinvf

Вычисляет обратную функцию ошибки _X

```cpp
inline float erfinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную функцию ошибки _X

## <a name="exp10"></a><a name="exp10"></a>exp10

Рассчитывает показатель базы-10 экспоненциально аргумента

```cpp
inline float exp10(float _X) restrict(amp);

inline double exp10(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает показатель базы-10 аргумента

## <a name="exp10f"></a><a name="exp10f"></a>exp10f

Рассчитывает показатель базы-10 экспоненциально аргумента

```cpp
inline float exp10f(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает показатель базы-10 аргумента

## <a name="expm1"></a><a name="expm1"></a>expm1

Вычисляет экспоненту аргумента с основанием e, за вычетом 1

```cpp
inline float expm1(float exponent) restrict(amp);

inline double expm1(double exponent) restrict(amp);
```

### <a name="parameters"></a>Параметры

*Экспоненты*<br/>
Экспоненциальный термин *n* `e`математического выражения <sup>n</sup>, где `e` является основанием естественного logarithm.

### <a name="return-value"></a>Возвращаемое значение

Возвращает экспоненту аргумента с основанием e, за вычетом 1

## <a name="expm1f"></a><a name="expm1f"></a>expm1f

Вычисляет экспоненту аргумента с основанием e, за вычетом 1

```cpp
inline float expm1f(float exponent) restrict(amp);
```

### <a name="parameters"></a>Параметры

*Экспоненты*<br/>
Экспоненциальный термин *n* `e`математического выражения <sup>n</sup>, где `e` является основанием естественного logarithm.

### <a name="return-value"></a>Возвращаемое значение

Возвращает экспоненту аргумента с основанием e, за вычетом 1

## <a name="exp"></a><a name="exp"></a>Exp

Вычисляет показатель базового экспоненциального аргумента

```cpp
inline float exp(float _X) restrict(amp);

inline double exp(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базовый экспоненциальный аргумент

## <a name="expf"></a><a name="expf"></a>expf

Вычисляет показатель базового экспоненциального аргумента

```cpp
inline float expf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базовый экспоненциальный аргумент

## <a name="exp2"></a><a name="exp2"></a>exp2

Рассчитывает показатель базы-2 экспоненциально аргумента

```cpp
inline float exp2(float _X) restrict(amp);

inline double exp2(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает 2 в степени, равной аргументу.

## <a name="exp2f"></a><a name="exp2f"></a>exp2f

Рассчитывает показатель базы-2 экспоненциально аргумента

```cpp
inline float exp2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает 2 в степени, равной аргументу.

## <a name="fabs"></a><a name="fabs"></a>фабс

Возвращает абсолютное значение аргумента

```cpp
inline float fabs(float _X) restrict(amp);

inline double fabs(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает абсолютное значение аргумента

## <a name="fabsf"></a><a name="fabsf"></a>фабсф

Возвращает абсолютное значение аргумента

```cpp
inline float fabsf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает абсолютное значение аргумента

## <a name="fdim"></a><a name="fdim"></a>fdim

Вычисляет положительную разницу между аргументами.

```cpp
inline float fdim(
   float _X,
   float _Y
) restrict(amp);
inline double fdim(
   double _X,
   double _Y
) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
значение плавающей точки *_Y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Разница между _X и _Y, если _X больше, чем _Y; в противном случае, 0 евро.

## <a name="fdimf"></a><a name="fdimf"></a>fdimf

Вычисляет положительную разницу между аргументами.

```cpp
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
значение плавающей точки *_Y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Разница между _X и _Y, если _X больше, чем _Y; в противном случае, 0 евро.

## <a name="floor"></a><a name="floor"></a>Этаже

Высчитывает пол аргумента

```cpp
inline float floor(float _X) restrict(amp);

inline double floor(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает пол аргумента

## <a name="floorf"></a><a name="floorf"></a>пол

Высчитывает пол аргумента

```cpp
inline float floorf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает пол аргумента

## <a name="a-namefma-fma"></a><a name="fma">Fma

Вычисляет продукт первого и второго указанных аргументов, затем добавляет к результату третий указанный аргумент; вся вычисления выполняется как одна операция.

```cpp
inline float fma(
   float _X,
   float _Y,
   float _Z
) restrict(amp);

inline double fma(
   double _X,
   double _Y,
   double _Z
) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Первый аргумент плавающей точки.
*_y*<br/>
Второй аргумент плавающей точки.
*_Z*<br/>
Третий аргумент плавающей точки.

### <a name="return-value"></a>Возвращаемое значение

Результат выражения (_X \* _Y) - _Z. Вся вычисления выполняется как одна операция; то есть, суб-выражения рассчитываются с бесконечной точностью, и только конечный результат округляется.

## <a name="fmaf"></a><a name="fmaf"></a>fmaf

Вычисляет продукт первого и второго указанных аргументов, затем добавляет к результату третий указанный аргумент; вся вычисления выполняется как одна операция.

```cpp
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Первый аргумент плавающей точки.
*_y*<br/>
Второй аргумент плавающей точки.
*_Z*<br/>
Третий аргумент плавающей точки.

### <a name="return-value"></a>Возвращаемое значение

Результат выражения (_X \* _Y) - _Z. Вся вычисления выполняется как одна операция; то есть, суб-выражения рассчитываются с бесконечной точностью, и только конечный результат округляется.

## <a name="fmax"></a><a name="fmax"></a>fmax

Определение максимального численного значения аргументов

```cpp
inline float fmax(
    float _X,
    float _Y) restrict(amp);

inline double fmax(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Вернуть максимальное числовое значение аргументов

## <a name="fmaxf"></a><a name="fmaxf"></a>fmaxf

Определение максимального численного значения аргументов

```cpp
inline float fmaxf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Вернуть максимальное числовое значение аргументов

## <a name="fmin"></a><a name="fmin"></a>fmin

Определение минимального численного значения аргументов

```cpp
inline float fmin(
    float _X,
    float _Y) restrict(amp);

inline double fmin(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Вернуть минимальное числовое значение аргументов

## <a name="fminf"></a><a name="fminf"></a>fminf

Определение минимального численного значения аргументов

```cpp
inline float fminf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Вернуть минимальное числовое значение аргументов

## <a name="fmod-function-c-amp"></a><a name="fmod"></a>функция fmod (СЗ АМП)

Вычисляет оставшуюся часть первого указанного аргумента, разделенного на второй указанный аргумент.

```cpp
inline float fmod(
    float _X,
    float _Y) restrict(amp);

inline double fmod(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Первый аргумент плавающей точки.

*_y*<br/>
Второй аргумент плавающей точки.

### <a name="return-value"></a>Возвращаемое значение

Остальная `_X` часть `_Y`разделена ; то есть, значение `_X`  -  `_Y` *n*, где *n* является целым целым таким образом, что величина `_X`  -  `_Y` *n* меньше, чем величина `_Y`.

## <a name="fmodf"></a><a name="fmodf"></a>fmodf

Вычисляет оставшуюся часть первого указанного аргумента, разделенного на второй указанный аргумент.

```cpp
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Первый аргумент плавающей точки.

*_y*<br/>
Второй аргумент плавающей точки.

### <a name="return-value"></a>Возвращаемое значение

Остальная `_X` часть `_Y`разделена ; то есть, значение `_X`  -  `_Y` *n*, где *n* является целым целым таким образом, что величина `_X`  -  `_Y` *n* меньше, чем величина `_Y`.

## <a name="fpclassify"></a><a name="fpclassify"></a>fpclassify

Классифицирует значение аргумента как NaN, бесконечное, нормальное, субнормальное, ноль

```cpp
inline int fpclassify(float _X) restrict(amp);

inline int fpclassify(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение макроса классификации чиномер, соответствующее значению аргумента.

## <a name="frexp"></a><a name="frexp"></a>frexp

Получает ментальную мантиссу и показатель _X

```cpp
inline float frexp(
    float _X,
    _Out_ int* _Exp) restrict(amp);

inline double frexp(
    double _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_Exp*<br/>
Возвращает неоценимый показатель _X в плавающем значении точки

### <a name="return-value"></a>Возвращаемое значение

Возвращает манти _Xссы

## <a name="frexpf"></a><a name="frexpf"></a>frexpf

Получает ментальную мантиссу и показатель _X

```cpp
inline float frexpf(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_Exp*<br/>
Возвращает неоценимый показатель _X в плавающем значении точки

### <a name="return-value"></a>Возвращаемое значение

Возвращает манти _Xссы

## <a name="hypot"></a><a name="hypot"></a>hypot

Вычисляет квадратный корень суммы квадратов _X и _Y

```cpp
inline float hypot(
    float _X,
    float _Y) restrict(amp);

inline double hypot(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает квадратный корень суммы квадратов _X и _Y

## <a name="hypotf"></a><a name="hypotf"></a>hypotf

Вычисляет квадратный корень суммы квадратов _X и _Y

```cpp
inline float hypotf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает квадратный корень суммы квадратов _X и _Y

## <a name="ilogb"></a><a name="ilogb"></a>ilogb

Извлеките экспонент _X как подписанное значение int

```cpp
inline int ilogb(float _X) restrict(amp);

inline int ilogb(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает экспонент _X как подписанное значение Int

## <a name="ilogbf"></a><a name="ilogbf"></a>ilogbf

Извлеките экспонент _X как подписанное значение int

```cpp
inline int ilogbf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает экспонент _X как подписанное значение Int

## <a name="isfinite"></a><a name="isfinite"></a>исфинит

Определяет, имеет ли аргумент конечное значение

```cpp
inline int isfinite(float _X) restrict(amp);

inline int isfinite(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение, если и только если аргумент имеет конечное значение

## <a name="isinf"></a><a name="isinf"></a>isinf

Определяет, является ли аргумент бесконечностью

```cpp
inline int isinf(float _X) restrict(amp);

inline int isinf(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение, если и только если аргумент имеет бесконечное значение

## <a name="isnan"></a><a name="isnan"></a>isnan

Определяет, является ли аргумент NaN

```cpp
inline int isnan(float _X) restrict(amp);

inline int isnan(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение, если и только если аргумент имеет значение NaN

## <a name="isnormal"></a><a name="isnormal"></a>isnormal

Определяет, является ли аргумент нормальным

```cpp
inline int isnormal(float _X) restrict(amp);

inline int isnormal(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение, если и только если аргумент имеет нормальное значение

## <a name="ldexp"></a><a name="ldexp"></a>ldexp

Вычисляет реальное число из указанной ментистии и экспонента.

```cpp
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);

inline double ldexp(
    double _X,
    double _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение плавающей точки, мантисса

*_Exp*<br/>
Значение, показательное значение

### <a name="return-value"></a>Возвращаемое значение

Возврат \* _X 2'_Exp

## <a name="ldexpf"></a><a name="ldexpf"></a>ldexpf

Вычисляет реальное число из указанной ментистии и экспонента.

```cpp
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение плавающей точки, мантисса

*_Exp*<br/>
Значение, показательное значение

### <a name="return-value"></a>Возвращаемое значение

Возврат \* _X 2'_Exp

## <a name="lgamma"></a><a name="lgamma"></a>lgamma

Вычисляет естественный logarithm абсолютного значения гаммы аргумента

```cpp
inline float lgamma(
    float _X,
    _Out_ int* _Sign) restrict(amp);

inline double lgamma(
    double _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_Sign*<br/>
Возвращает знак

### <a name="return-value"></a>Возвращаемое значение

Возвращает естественный logarithm абсолютного значения гаммы аргумента

## <a name="lgammaf"></a><a name="lgammaf"></a>lgammaf

Вычисляет естественный logarithm абсолютного значения гаммы аргумента

```cpp
inline float lgammaf(
    float _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_Sign*<br/>
Возвращает знак

### <a name="return-value"></a>Возвращаемое значение

Возвращает естественный logarithm абсолютного значения гаммы аргумента

## <a name="log"></a><a name="log"></a>Журнала

Вычисляет базовый-e logarithm аргумента

```cpp
inline float log(float _X) restrict(amp);

inline double log(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базовый-e logarithm аргумента

## <a name="log10"></a><a name="log10"></a>log10

Рассчитывает базу-10 logarithm аргумента

```cpp
inline float log10(float _X) restrict(amp);

inline double log10(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базу-10 logarithm аргумента

## <a name="log10f"></a><a name="log10f"></a>log10f

Рассчитывает базу-10 logarithm аргумента

```cpp
inline float log10f(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базу-10 logarithm аргумента

## <a name="log1p"></a><a name="log1p"></a>log1p

Рассчитывает базовый-e logarithm 1 плюс аргумент

```cpp
inline float log1p(float _X) restrict(amp);

inline double log1p(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базовый-e logarithm 1 плюс аргумент

## <a name="log1pf"></a><a name="log1pf"></a>log1pf

Рассчитывает базовый-e logarithm 1 плюс аргумент

```cpp
inline float log1pf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базовый-e logarithm 1 плюс аргумент

## <a name="log2"></a><a name="log2"></a>log2

Рассчитывает базу-2 logarithm аргумента

```cpp
inline float log2(float _X) restrict(amp);

inline double log2(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базу-10 logarithm аргумента

## <a name="log2f"></a><a name="log2f"></a>log2f

Рассчитывает базу-2 logarithm аргумента

```cpp
inline float log2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базу-10 logarithm аргумента

## <a name="logb"></a><a name="logb"></a>бревенчатый журнал

Извлекает экспонент _X, как подписанное значение целых в формате плавающей точки

```cpp
inline float logb(float _X) restrict(amp);

inline double logb(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает подписанный показатель _X

## <a name="logbf"></a><a name="logbf"></a>logbf

Извлекает экспонент _X, как подписанное значение целых в формате плавающей точки

```cpp
inline float logbf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает подписанный показатель _X

## <a name="logf"></a><a name="logf"></a>logf

Вычисляет базовый-e logarithm аргумента

```cpp
inline float logf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базовый-e logarithm аргумента

## <a name="modf"></a><a name="modf"></a>modf

Разделяет указанный аргумент на дробные и нестыковкие части.

```cpp
inline float modf(
    float _X,
    _Out_ float* _Iptr) restrict(amp);

inline double modf(
    double _X,
    _Out_ double* _Iptr) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_Iptr*<br/>
(ваут) Целый ряд `_X`, как плавающая точка значение.

### <a name="return-value"></a>Возвращаемое значение

Подписанная дробная `_X`часть .

## <a name="modff"></a><a name="modff"></a>modff

Разделяет указанный аргумент на дробные и нестыковкие части.

```cpp
inline float modff(
    float _X,
    _Out_ float* _Iptr) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_Iptr*<br/>
Целый ряд `_X`, как плавающая точка значение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает подписанную дробную часть `_X`.

## <a name="nan"></a><a name="nan"></a>Nan

Возвращает тихий NaN

```cpp
inline double nan(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает тихий NaN, если таковой имеется, с содержанием, указанным в _X

## <a name="nanf"></a><a name="nanf"></a>нанф

Возвращает тихий NaN

```cpp
inline float nanf(int _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает тихий NaN, если таковой имеется, с содержанием, указанным в _X

## <a name="nearbyint"></a><a name="nearbyint"></a>поблизости

Округляет аргумент до самого разного значения в формате плавающей точки, используя текущее направление округления.

```cpp
inline float nearbyint(float _X) restrict(amp);

inline double nearbyint(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает округленное значение атлет.

## <a name="nearbyintf"></a><a name="nearbyintf"></a>поблизостиintf

Округляет аргумент до самого разного значения в формате плавающей точки, используя текущее направление округления.

```cpp
inline float nearbyintf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает округленное значение атлет.

## <a name="nextafter"></a><a name="nextafter"></a>в следующий раз

Определите следующее представленное значение, в типе функции, после _X в направлении _Y

```cpp
inline float nextafter(
    float _X,
    float _Y) restrict(amp);

inline double nextafter(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает следующее представленное значение, в типе функции, после _X в направлении _Y

## <a name="nextafterf"></a><a name="nextafterf"></a>nextafterf

Определите следующее представленное значение, в типе функции, после _X в направлении _Y

```cpp
inline float nextafterf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает следующее представленное значение, в типе функции, после _X в направлении _Y

## <a name="phi"></a><a name="phi"></a>Phi

Возвращает функцию кумулятивного распределения аргумента

```cpp
inline float phi(float _X) restrict(amp);

inline double phi(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает функцию кумулятивного распределения аргумента

## <a name="phif"></a><a name="phif"></a>phif

Возвращает функцию кумулятивного распределения аргумента

```cpp
inline float phif(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает функцию кумулятивного распределения аргумента

## <a name="pow"></a><a name="pow"></a>Trs

Расчеты _X подняты до власти _Y

```cpp
inline float pow(
    float _X,
    float _Y) restrict(amp);

inline double pow(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение плавающей точки, база

*_y*<br/>
Значение плавающей точки, показательное значение

### <a name="return-value"></a>Возвращаемое значение

## <a name="powf"></a><a name="powf"></a>powf

Расчеты _X подняты до власти _Y

```cpp
inline float powf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение плавающей точки, база

*_y*<br/>
Значение плавающей точки, показательное значение

### <a name="return-value"></a>Возвращаемое значение

## <a name="probit"></a><a name="probit"></a>пробит

Возвращает обратную функцию кумулятивного распределения аргумента

```cpp
inline float probit(float _X) restrict(amp);

inline double probit(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную функцию кумулятивного распределения аргумента

## <a name="probitf"></a><a name="probitf"></a>probitf

Возвращает обратную функцию кумулятивного распределения аргумента

```cpp
inline float probitf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную функцию кумулятивного распределения аргумента

## <a name="rcbrt"></a><a name="rcbrt"></a>rcbrt

Возвращает взаимный корень куба аргумента

```cpp
inline float rcbrt(float _X) restrict(amp);

inline double rcbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает взаимный корень куба аргумента

## <a name="rcbrtf"></a><a name="rcbrtf"></a>rcbrtf

Возвращает взаимный корень куба аргумента

```cpp
inline float rcbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает взаимный корень куба аргумента

## <a name="remainder"></a><a name="remainder"></a>Остаток

Вычисляет оставшуюся часть: _X REM _Y

```cpp
inline float remainder(
    float _X,
    float _Y) restrict(amp);

inline double remainder(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X REM _Y

## <a name="remainderf"></a><a name="remainderf"></a>remainderf

Вычисляет оставшуюся часть: _X REM _Y

```cpp
inline float remainderf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X REM _Y

## <a name="remquo"></a><a name="remquo"></a>remquo

Вычисляет оставшуюся часть первого указанного аргумента, разделенного на второй указанный аргумент. Также вычисляет фактор significand первого указанного аргумента разделенного significand второго указанного аргумента, и возвращает фактор используя положение указанное в третьем аргументе.

```cpp
inline float remquo(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);

inline double remquo(
    double _X,
    double _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Первый аргумент плавающей точки.

*_y*<br/>
Второй аргумент плавающей точки.

*_Quo*<br/>
(ваут) Адрес несколько, который используется для возвращения фактора дробных битов `_X` разделены дробные биты `_Y`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает оставшуюся `_X` `_Y`часть делится на .

## <a name="remquof"></a><a name="remquof"></a>remquof

Вычисляет оставшуюся часть первого указанного аргумента, разделенного на второй указанный аргумент. Также вычисляет фактор significand первого указанного аргумента разделенного significand второго указанного аргумента, и возвращает фактор используя положение указанное в третьем аргументе.

```cpp
inline float remquof(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Первый аргумент плавающей точки.

*_y*<br/>
Второй аргумент плавающей точки.

*_Quo*<br/>
(ваут) Адрес несколько, который используется для возвращения фактора дробных битов `_X` разделены дробные биты `_Y`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает оставшуюся `_X` `_Y`часть делится на .

## <a name="round"></a><a name="round"></a>Круглый

Раунды _X до ближайшего многоглавого

```cpp
inline float round(float _X) restrict(amp);

inline double round(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ближайшую часть _X

## <a name="roundf"></a><a name="roundf"></a>roundf

Раунды _X до ближайшего многоглавого

```cpp
inline float roundf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ближайшую часть _X

## <a name="rsqrt"></a><a name="rsqrt"></a>rsqrt

Возвращает взаимный квадратный корень аргумента

```cpp
inline float rsqrt(float _X) restrict(amp);

inline double rsqrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает взаимный квадратный корень аргумента

## <a name="rsqrtf"></a><a name="rsqrtf"></a>rsqrtf

Возвращает взаимный квадратный корень аргумента

```cpp
inline float rsqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает взаимный квадратный корень аргумента

## <a name="scalb"></a><a name="scalb"></a>scalb

Умножает _X на FLT_RADIX к _Y власти

```cpp
inline float scalb(
    float _X,
    float _Y) restrict(amp);

inline double scalb(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвраты \* _X (FLT_RADIX и _Y)

## <a name="scalbf"></a><a name="scalbf"></a>scalbf

Умножает _X на FLT_RADIX к _Y власти

```cpp
inline float scalbf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвраты \* _X (FLT_RADIX и _Y)

## <a name="scalbn"></a><a name="scalbn"></a>scalbn

Умножает _X на FLT_RADIX к _Y власти

```cpp
inline float scalbn(
    float _X,
    int _Y) restrict(amp);

inline double scalbn(
    double _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвраты \* _X (FLT_RADIX и _Y)

## <a name="scalbnf"></a><a name="scalbnf"></a>scalbnf

Умножает _X на FLT_RADIX к _Y власти

```cpp
inline float scalbnf(
    float _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвраты \* _X (FLT_RADIX и _Y)

## <a name="signbit"></a><a name="signbit"></a>signbit

Определяет, является ли признак _X отрицательным

```cpp
inline int signbit(float _X) restrict(amp);

inline int signbit(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение, если и только если признак _X отрицательный

## <a name="signbitf"></a><a name="signbitf"></a>signbitf

Определяет, является ли признак _X отрицательным

```cpp
inline int signbitf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение, если и только если признак _X отрицательный

## <a name="sin"></a><a name="sin"></a>Грех

Рассчитывает синусоидное значение аргумента

```cpp
inline float sin(float _X) restrict(amp);

inline double sin(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает синусоидное значение аргумента

## <a name="sinf"></a><a name="sinf"></a>синф

Рассчитывает синусоидное значение аргумента

```cpp
inline float sinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает синусоидное значение аргумента

## <a name="sincos"></a><a name="sincos"></a>синкосы

Рассчитывает синусоидную и косивную ценность _X

```cpp
inline void sincos(
    float _X,
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);

inline void sincos(
    double _X,
    _Out_ double* _S,
    _Out_ double* _C) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_s*<br/>
Возвращает синусоидное значение _X

*_C*<br/>
Возвращает косиновый значение _X

## <a name="sincosf"></a><a name="sincosf"></a>sincosf

Рассчитывает синусоидную и косивную ценность _X

```cpp
inline void sincosf(
    float _X,
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_s*<br/>
Возвращает синусоидное значение _X

*_C*<br/>
Возвращает косиновый значение _X

## <a name="sinh"></a><a name="sinh"></a>Sinh

Рассчитывает гиперболическую синусоидную ценность аргумента

```cpp
inline float sinh(float _X) restrict(amp);

inline double sinh(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает гиперболическую синусоидную ценность аргумента

## <a name="sinhf"></a><a name="sinhf"></a>синхф

Рассчитывает гиперболическую синусоидную ценность аргумента

```cpp
inline float sinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает гиперболическую синусоидную ценность аргумента

## <a name="sinpi"></a><a name="sinpi"></a>синпи

Рассчитывает синусоидное \* значение пи _X

```cpp
inline float sinpi(float _X) restrict(amp);

inline double sinpi(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает синусоидное значение пи \* _X

## <a name="sinpif"></a><a name="sinpif"></a>синпиф

Рассчитывает синусоидное \* значение пи _X

```cpp
inline float sinpif(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает синусоидное значение пи \* _X

## <a name="sqrt"></a><a name="sqrt"></a>Sqrt

Высчитывает корень шквала аргумента

```cpp
inline float sqrt(float _X) restrict(amp);

inline double sqrt(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает корень шквала аргумента

## <a name="sqrtf"></a><a name="sqrtf"></a>sqrtf

Высчитывает корень шквала аргумента

```cpp
inline float sqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает корень шквала аргумента

## <a name="tan"></a><a name="tan"></a>Загар

Рассчитывает касательное значение аргумента

```cpp
inline float tan(float _X) restrict(amp);

inline double tan(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает касательное значение аргумента

## <a name="tanf"></a><a name="tanf"></a>танф

Рассчитывает касательное значение аргумента

```cpp
inline float tanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает касательное значение аргумента

## <a name="tanh"></a><a name="tanh"></a>тан

Рассчитывает гиперболическую касательную ценность аргумента

```cpp
inline float tanh(float _X) restrict(amp);

inline double tanh(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает гиперболическую касательную ценность аргумента

## <a name="tanhf"></a><a name="tanhf"></a>tanhf

Рассчитывает гиперболическую касательную ценность аргумента

```cpp
inline float tanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает гиперболическую касательную ценность аргумента

## <a name="tanpi"></a><a name="tanpi"></a>танпи

Рассчитывает касательное значение \* пи _X

```cpp
inline float tanpi(float _X) restrict(amp);

inline double tanpi(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает касательное \* значение пи _X

## <a name="tanpif"></a><a name="tanpif"></a>танпиф

Рассчитывает касательное значение \* пи _X

```cpp
inline float tanpif(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает касательное \* значение пи _X

## <a name="tgamma"></a><a name="tgamma"></a>tgamma

Вычисляет гамма-функцию _X

```cpp
inline float tgamma(float _X) restrict(amp);

inline double tgamma(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат гамма-функции _X

## <a name="tgammaf"></a><a name="tgammaf"></a>tgammaf

Вычисляет гамма-функцию _X

```cpp
inline float tgammaf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат гамма-функции _X

## <a name="trunc"></a><a name="trunc"></a>Trunc

Truncates аргумент к компоненту integer

```cpp
inline float trunc(float _X) restrict(amp);

inline double trunc(double _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает инкеме компонент аргумента

## <a name="truncf"></a><a name="truncf"></a>truncf

Truncates аргумент к компоненту integer

```cpp
inline float truncf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает инкеме компонент аргумента

## <a name="see-also"></a>См. также раздел

[Параллелизм::precise-math Namespace](concurrency-precise-math-namespace.md)
