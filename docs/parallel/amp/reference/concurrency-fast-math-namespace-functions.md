---
title: Функции пространства имен Concurrency::fast_math
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::fast_math::acos
- amp_math/Concurrency::fast_math::asin
- amp_math/Concurrency::fast_math::asinf
- amp_math/Concurrency::fast_math::atan2
- amp_math/Concurrency::fast_math::atan2f
- amp_math/Concurrency::fast_math::ceil
- amp_math/Concurrency::fast_math::ceilf
- amp_math/Concurrency::fast_math::cosf
- amp_math/Concurrency::fast_math::cosh
- amp_math/Concurrency::fast_math::exp
- amp_math/Concurrency::fast_math::exp2
- amp_math/Concurrency::fast_math::expf
- amp_math/Concurrency::fast_math::fabs
- amp_math/Concurrency::fast_math::floor
- amp_math/Concurrency::fast_math::floorf
- amp_math/Concurrency::fast_math::fmaxf
- amp_math/Concurrency::fast_math::fmin
- amp_math/Concurrency::fast_math::fmod
- amp_math/Concurrency::fast_math::fmodf
- amp_math/Concurrency::fast_math::frexpf
- amp_math/Concurrency::fast_math::isfinite
- amp_math/Concurrency::fast_math::isnan
- amp_math/Concurrency::fast_math::ldexp
- amp_math/Concurrency::fast_math::log
- amp_math/Concurrency::fast_math::log10
- amp_math/Concurrency::fast_math::log2
- amp_math/Concurrency::fast_math::log2f
- amp_math/Concurrency::fast_math::modf
- amp_math/Concurrency::fast_math::modff
- amp_math/Concurrency::fast_math::powf
- amp_math/Concurrency::fast_math::round
- amp_math/Concurrency::fast_math::rsqrt
- amp_math/Concurrency::fast_math::rsqrtf
- amp_math/Concurrency::fast_math::signbitf
- amp_math/Concurrency::fast_math::sin
- amp_math/Concurrency::fast_math::sincosf
- amp_math/Concurrency::fast_math::sinf
- amp_math/Concurrency::fast_math::sinhf
- amp_math/Concurrency::fast_math::sqrt
- amp_math/Concurrency::fast_math::tan
- amp_math/Concurrency::fast_math::tanf
- amp_math/Concurrency::fast_math::tanhf
- amp_math/Concurrency::fast_math::trunc
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
ms.openlocfilehash: fa024c781804d404870a0362a027e1bc436902ef
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667640"
---
# <a name="concurrencyfastmath-namespace-functions"></a>Функции пространства имен Concurrency::fast_math

||||
|-|-|-|
|[acos](#acos)|[acosf](#acosf)|[asin](#asin)|
|[asinf](#asinf)|[atan](#atan)|[atan2](#atan2)|
|[atan2f](#atan2f)|[atanf](#atanf)|[ceil](#ceil)|
|[ceilf](#ceilf)|[cos](#cos)|[cosf](#cosf)|
|[cosh](#cosh)|[coshf](#coshf)|[exp](#exp)|
|[exp2](#exp2)|[exp2f](#exp2f)|[expf](#expf)|
|[fabs](#fabs)|[fabsf](#fabsf)|[floor](#floor)|
|[floorf](#floorf)|[fmax](#fmax)|[fmaxf](#fmaxf)|
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|
|[fmodf](#fmodf)|[frexp](#frexp)|[frexpf](#frexpf)|
|[isfinite](#isfinite)|[isinf](#isinf)|[isnan](#isnan)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[log](#log)|
|[log10](#log10)|[log10f](#log10f)|[log2](#log2)|
|[log2f](#log2f)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[pow](#pow)|[powf](#powf)|
|[round](#round)|[roundf](#roundf)|[rsqrt](#rsqrt)|
|[rsqrtf](#rsqrtf)|[signbit](#signbit)|[signbitf](#signbitf)|
|[sin](#sin)|[sincos](#sincos)|[sincosf](#sincosf)|
|[sinf](#sinf)|[sinh](#sinh)|[sinhf](#sinhf)|
|[sqrt](#sqrt)|[sqrtf](#sqrtf)|[tan](#tan)|
|[tanf](#tanf)|[tanh](#tanh)|[tanhf](#tanhf)|
|[trunc](#trunc)|[truncf](#truncf)|

##  <a name="acos"></a>  acos

Вычисляет арккосинус аргумента

```
inline float acos(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арккосинуса аргумента

##  <a name="acosf"></a>  acosf

Вычисляет арккосинус аргумента

```
inline float acosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арккосинуса аргумента

##  <a name="asin"></a>  asin

Вычисляет гиперболический арксинус аргумента

```
inline float asin(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арксинуса аргумента

##  <a name="asinf"></a>  asinf

Вычисляет гиперболический арксинус аргумента

```
inline float asinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арксинуса аргумента

##  <a name="atan"></a>  atan

Вычисляет арктангенс аргумента.

```
inline float atan(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арктангенса аргумента

##  <a name="atan2"></a>  atan2

Вычисляет арктангенс _Y/_X

```
inline float atan2(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Y*<br/>
Значение с плавающей запятой

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арктангенса _Y/_X

##  <a name="atan2f"></a>  atan2f

Вычисляет арктангенс _Y/_X

```
inline float atan2f(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Y*<br/>
Значение с плавающей запятой

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арктангенса _Y/_X

##  <a name="atanf"></a>  atanf

Вычисляет арктангенс аргумента.

```
inline float atanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение арктангенса аргумента

##  <a name="ceil"></a>  ceil

Вычисляет максимальное значение аргумента

```
inline float ceil(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает максимальное значение аргумента

##  <a name="ceilf"></a>  ceilf

Вычисляет максимальное значение аргумента

```
inline float ceilf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает максимальное значение аргумента

##  <a name="cosf"></a>  cosf

Вычисляет косинус аргумента

```
inline float cosf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение косинуса аргумента

##  <a name="coshf"></a>  coshf

Вычисляет значение гиперболического косинуса аргумента

```
inline float coshf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического косинуса аргумента

##  <a name="cos"></a>  cos

Вычисляет косинус аргумента

```
inline float cos(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение косинуса аргумента

##  <a name="cosh"></a>  cosh

Вычисляет значение гиперболического косинуса аргумента

```
inline float cosh(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического косинуса аргумента

##  <a name="exp"></a>  exp

Вычисляет экспоненту аргумента base-e

```
inline float exp(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает экспоненту аргумента с основанием e

##  <a name="exp2"></a>  exp2

Вычисляет экспоненту аргумента base-2

```
inline float exp2(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает 2 в степени, равной аргументу

##  <a name="exp2f"></a>  exp2f

Вычисляет экспоненту аргумента base-2

```
inline float exp2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает 2 в степени, равной аргументу

##  <a name="expf"></a>  expf

Вычисляет экспоненту аргумента base-e

```
inline float expf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает экспоненту аргумента с основанием e

##  <a name="fabs"></a>  fabs

Возвращает абсолютное значение аргумента

```
inline float fabs(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает абсолютное значение аргумента

##  <a name="fabsf"></a>  fabsf

Возвращает абсолютное значение аргумента

```
inline float fabsf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает абсолютное значение аргумента

##  <a name="floor"></a>  функция FLOOR

Вычисляет минимальное значение аргумента

```
inline float floor(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает минимальное значение аргумента

##  <a name="floorf"></a>  floorf

Вычисляет минимальное значение аргумента

```
inline float floorf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает минимальное значение аргумента

##  <a name="fmax"></a>  fmax

Определение максимального числового значения аргументов

```
inline float max(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает максимальное числовое значение аргументов

##  <a name="fmaxf"></a>  fmaxf

Определение максимального числового значения аргументов

```
inline float fmaxf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает максимальное числовое значение аргументов

##  <a name="fmin"></a>  fmin

Определение минимального числового значения аргументов

```
inline float min(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Целочисленное значение

*_Y*<br/>
Целочисленное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает минимальное числовое значение аргументов

##  <a name="fminf"></a>  fminf

Определение минимального числового значения аргументов

```
inline float fminf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает минимальное числовое значение аргументов

##  <a name="fmod"></a>  fmod

Вычисляет остаток с плавающей запятой от _X/_Y

```
inline float fmod(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает остаток с плавающей запятой от _X/_Y

##  <a name="fmodf"></a>  fmodf

Вычисляет остаток с плавающей запятой от _X/_Y.

```
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает остаток с плавающей запятой от _X/_Y

##  <a name="frexp"></a>  frexp

Получает мантиссу и экспоненту _X

```
inline float frexp(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Exp*<br/>
Возвращает экспоненту _X целое число со знаком в значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X мантиссы

##  <a name="frexpf"></a>  frexpf

Получает мантиссу и экспоненту _X

```
inline float frexpf(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Exp*<br/>
Возвращает экспоненту _X целое число со знаком в значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X мантиссы

##  <a name="isfinite"></a>  isfinite

Определяет, имеет ли аргумент конечное значение

```
inline int isfinite(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение только в том случае, если аргумент имеет конечное значение

##  <a name="isinf"></a>  isinf

Определяет, является ли аргумент бесконечности

```
inline int isinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение только в том случае, если аргумент имеет бесконечное значение

##  <a name="isnan"></a>  isNaN

Определяет, является ли аргумент значение NaN

```
inline int isnan(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение только в том случае, если аргумент имеет значение NaN

##  <a name="ldexp"></a>  ldexp

Вычисляет действительное число на основе мантиссы и экспоненты

```
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой, mentissa

*_Exp*<br/>
Целый показатель степени

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X \* 2 ^ _Exp

##  <a name="ldexpf"></a>  ldexpf

Вычисляет действительное число на основе мантиссы и экспоненты

```
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой, mentissa

*_Exp*<br/>
Целый показатель степени

### <a name="return-value"></a>Возвращаемое значение

Возвращает _X \* 2 ^ _Exp

##  <a name="log"></a>  log

Вычисляет логарифм с основанием e аргумента

```
inline float log(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает логарифм с основанием e аргумента

##  <a name="log10"></a>  log10

Вычисляет десятичный логарифм аргумента

```
inline float log10(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает десятичный логарифм аргумента

##  <a name="log10f"></a>  log10f

Вычисляет десятичный логарифм аргумента

```
inline float log10f(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает десятичный логарифм аргумента

##  <a name="log2"></a>  log2

Вычисляет логарифм аргумента

```
inline float log2(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает логарифм аргумента

##  <a name="log2f"></a>  log2f

Вычисляет логарифм аргумента

```
inline float log2f(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает десятичный логарифм аргумента

##  <a name="logf"></a>  logf

Вычисляет логарифм с основанием e аргумента

```
inline float logf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает логарифм с основанием e аргумента

##  <a name="modf"></a>  modf

Разбивает _X на дробную и целую части.

```
inline float modf(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Кластера*<br/>
Получает часть значения в целое число

### <a name="return-value"></a>Возвращаемое значение

Возвращает дробную часть со знаком _X

##  <a name="modff"></a>  modff

Разбивает _X на дробную и целую части.

```
inline float modff(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_Кластера*<br/>
Получает часть значения в целое число

### <a name="return-value"></a>Возвращаемое значение

Возвращает дробную часть со знаком _X

##  <a name="pow"></a>  pow

Возводит _X в степень _Y

```
inline float pow(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой, базовый

*_Y*<br/>
Значение с плавающей запятой, показатель степени

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение _X, возведенное в степень _Y

##  <a name="powf"></a>  powf

Возводит _X в степень _Y

```
inline float powf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой, базовый

*_Y*<br/>
Значение с плавающей запятой, показатель степени

### <a name="return-value"></a>Возвращаемое значение

##  <a name="round"></a>  Округление

Округляет _X до ближайшего целого числа

```
inline float round(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ближайшего целого значения _X

##  <a name="roundf"></a>  roundf

Округляет _X до ближайшего целого числа

```
inline float roundf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ближайшего целого значения _X

##  <a name="rsqrt"></a>  rsqrt

Возвращает обратную величину квадратного корня из аргумента

```
inline float rsqrt(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную величину квадратного корня из аргумента

##  <a name="rsqrtf"></a>  rsqrtf

Возвращает обратную величину квадратного корня из аргумента

```
inline float rsqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает обратную величину квадратного корня из аргумента

##  <a name="signbit"></a>  signbit

Определяет, является ли отрицательный знак _X

```
inline int signbit(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение только в том случае, если знак _X является отрицательным

##  <a name="signbitf"></a>  signbitf

Определяет, является ли отрицательный знак _X

```
inline int signbitf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение только в том случае, если знак _X является отрицательным

##  <a name="sin"></a>  sin

Вычисляет значение синуса аргумента

```
inline float sin(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение синуса аргумента

##  <a name="sinf"></a>  sinf

Вычисляет значение синуса аргумента

```
inline float sinf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение синуса аргумента

##  <a name="sincos"></a>  sincos

Вычисляет значение синуса и косинуса _X

```
inline void sincos(
    float _X,
    float* _S,
    float* _C) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_S*<br/>
Возвращает значение синуса _X

*_О*<br/>
Возвращает значение косинуса _X

##  <a name="sincosf"></a>  sincosf

Вычисляет значение синуса и косинуса _X

```
inline void sincosf(
    float _X,
    float* _S,
    float* _C) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

*_S*<br/>
Возвращает значение синуса _X

*_О*<br/>
Возвращает значение косинуса _X

##  <a name="sinh"></a>  sinh

Вычисляет значение гиперболического синуса аргумента

```
inline float sinh(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического синуса аргумента

##  <a name="sinhf"></a>  sinhf

Вычисляет значение гиперболического синуса аргумента

```
inline float sinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического синуса аргумента

##  <a name="sqrt"></a>  sqrt

Вычисляет squre корень аргумента

```
inline float sqrt(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает корень squre аргумента

##  <a name="sqrtf"></a>  sqrtf

Вычисляет squre корень аргумента

```
inline float sqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает корень squre аргумента

##  <a name="tan"></a>  tan

Вычисляет значение тангенса аргумента

```
inline float tan(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение тангенса аргумента

##  <a name="tanf"></a>  tanf

Вычисляет значение тангенса аргумента

```
inline float tanf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение тангенса аргумента

##  <a name="tanh"></a>  tanh

Вычисляет значение гиперболического тангенса аргумента

```
inline float tanh(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического тангенса аргумента

##  <a name="tanhf"></a>  tanhf

Вычисляет значение гиперболического тангенса аргумента

```
inline float tanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение гиперболического тангенса аргумента

##  <a name="trunc"></a>  TRUNC

Усекает аргумент до целой

```
inline float trunc(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает компонент целочисленный аргумент

##  <a name="truncf"></a>  truncf

Усекает аргумент до целой

```
inline float truncf(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_X*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает компонент целочисленный аргумент

## <a name="requirements"></a>Требования

**Заголовок:** amp_math.h **пространство имен:** Concurrency::fast_math

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::fast_math](concurrency-fast-math-namespace.md)
