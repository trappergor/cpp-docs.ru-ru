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
ms.openlocfilehash: cd0882b072cfe26cd83e63024ae6837dc962ebf9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376398"
---
# <a name="concurrencyfast_math-namespace-functions"></a>Функции пространства имен Concurrency::fast_math

||||
|-|-|-|
|[акос](#acos)|[acosf](#acosf)|[Asin](#asin)|
|[asinf](#asinf)|[Atan](#atan)|[atan2](#atan2)|
|[atan2f](#atan2f)|[atanf](#atanf)|[ceil](#ceil)|
|[ceilf](#ceilf)|[Потому что](#cos)|[cosf](#cosf)|
|[cosh](#cosh)|[coshf](#coshf)|[Exp](#exp)|
|[exp2](#exp2)|[exp2f](#exp2f)|[expf](#expf)|
|[fabs](#fabs)|[fabsf](#fabsf)|[Этаже](#floor)|
|[floorf](#floorf)|[fmax](#fmax)|[fmaxf](#fmaxf)|
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|
|[fmodf](#fmodf)|[frexp](#frexp)|[frexpf](#frexpf)|
|[исфинит](#isfinite)|[isinf](#isinf)|[isnan](#isnan)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[Журнала](#log)|
|[log10](#log10)|[log10f](#log10f)|[log2](#log2)|
|[log2f](#log2f)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[pow](#pow)|[powf](#powf)|
|[Круглый](#round)|[roundf](#roundf)|[rsqrt](#rsqrt)|
|[rsqrtf](#rsqrtf)|[signbit](#signbit)|[signbitf](#signbitf)|
|[Грех](#sin)|[синкосы](#sincos)|[sincosf](#sincosf)|
|[sinf](#sinf)|[sinh](#sinh)|[sinhf](#sinhf)|
|[Sqrt](#sqrt)|[sqrtf](#sqrtf)|[Загар](#tan)|
|[tanf](#tanf)|[тан](#tanh)|[tanhf](#tanhf)|
|[Trunc](#trunc)|[truncf](#truncf)|

## <a name="acos"></a><a name="acos"></a>акос

Вычисляет арккосин аргумента

```cpp
inline float acos(float _X) restrict(amp);
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

## <a name="asin"></a><a name="asin"></a>Asin

Вычисляет дуги аргумента

```cpp
inline float asin(float _X) restrict(amp);
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

## <a name="atan"></a><a name="atan"></a>Atan

Вычисляет арктангенс аргумента.

```cpp
inline float atan(float _X) restrict(amp);
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

## <a name="ceil"></a><a name="ceil"></a>ceil

Высчитывает потолок аргумента

```cpp
inline float ceil(float _X) restrict(amp);
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

## <a name="cos"></a><a name="cos"></a>Потому что

Вычисляет косинус аргумента.

```cpp
inline float cos(float _X) restrict(amp);
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
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает гиперболическую косиновую ценность аргумента

## <a name="exp"></a><a name="exp"></a>Exp

Вычисляет показатель базового экспоненциального аргумента

```cpp
inline float exp(float _X) restrict(amp);
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

## <a name="fabs"></a><a name="fabs"></a>фабс

Возвращает абсолютное значение аргумента

```cpp
inline float fabs(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

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

## <a name="floor"></a><a name="floor"></a>Этаже

Высчитывает пол аргумента

```cpp
inline float floor(float _X) restrict(amp);
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

## <a name="fmax"></a><a name="fmax"></a>fmax

Определение максимального численного значения аргументов

```cpp
inline float max(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

*_y*<br/>
Целочисленное значение

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
inline float min(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Целочисленное значение

*_y*<br/>
Целочисленное значение

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

## <a name="fmod"></a><a name="fmod"></a>Fmod

Вычисляет остаток плавающей точки _X/_Y

```cpp
inline float fmod(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает остаток плавающей точки _X/_Y

## <a name="fmodf"></a><a name="fmodf"></a>fmodf

Вычисляет остаток плавающей точки _X/_Y.

```cpp
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_y*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает остаток плавающей точки _X/_Y

## <a name="frexp"></a><a name="frexp"></a>frexp

Получает ментальную мантиссу и показатель _X

```cpp
inline float frexp(
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

## <a name="isfinite"></a><a name="isfinite"></a>исфинит

Определяет, имеет ли аргумент конечное значение

```cpp
inline int isfinite(float _X) restrict(amp);
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
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение, если и только если аргумент имеет значение NaN

## <a name="ldexp"></a><a name="ldexp"></a>ldexp

Вычисляет реальное число из мантиссы и экспонента

```cpp
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение плавающей точки, ментисса

*_Exp*<br/>
Показатель Integer

### <a name="return-value"></a>Возвращаемое значение

Возврат \* _X 2'_Exp

## <a name="ldexpf"></a><a name="ldexpf"></a>ldexpf

Вычисляет реальное число из мантиссы и экспонента

```cpp
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение плавающей точки, ментисса

*_Exp*<br/>
Показатель Integer

### <a name="return-value"></a>Возвращаемое значение

Возврат \* _X 2'_Exp

## <a name="log"></a><a name="log"></a>Журнала

Вычисляет базовый-e logarithm аргумента

```cpp
inline float log(float _X) restrict(amp);
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

## <a name="log2"></a><a name="log2"></a>log2

Рассчитывает базу-2 logarithm аргумента

```cpp
inline float log2(float _X) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение

Возвращает базу-2 logarithm аргумента

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

Сплиты _X на дробные и многоразовые части.

```cpp
inline float modf(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_Ip*<br/>
Получает несоразмереную часть стоимости

### <a name="return-value"></a>Возвращаемое значение

Возвращает подписанную дробную часть _X

## <a name="modff"></a><a name="modff"></a>modff

Сплиты _X на дробные и многоразовые части.

```cpp
inline float modff(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение с плавающей запятой

*_Ip*<br/>
Получает несоразмереную часть стоимости

### <a name="return-value"></a>Возвращаемое значение

Возвращает подписанную дробную часть _X

## <a name="pow"></a><a name="pow"></a>Trs

Расчеты _X подняты до власти _Y

```cpp
inline float pow(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_x*<br/>
Значение плавающей точки, база

*_y*<br/>
Значение плавающей точки, показательное значение

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение _X, поднятого на мощность _Y

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

## <a name="round"></a><a name="round"></a>Круглый

Раунды _X до ближайшего многоглавого

```cpp
inline float round(float _X) restrict(amp);
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

## <a name="signbit"></a><a name="signbit"></a>signbit

Определяет, является ли признак _X отрицательным

```cpp
inline int signbit(float _X) restrict(amp);
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
    float* _S,
    float* _C) restrict(amp);
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
    float* _S,
    float* _C) restrict(amp);
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

## <a name="sqrt"></a><a name="sqrt"></a>Sqrt

Высчитывает корень шквала аргумента

```cpp
inline float sqrt(float _X) restrict(amp);
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

## <a name="trunc"></a><a name="trunc"></a>Trunc

Truncates аргумент к компоненту integer

```cpp
inline float trunc(float _X) restrict(amp);
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

## <a name="requirements"></a>Требования

**Заголовок:** amp_math.h **Namespace:** Параллель:::fast_math

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency::fast_math](concurrency-fast-math-namespace.md)
