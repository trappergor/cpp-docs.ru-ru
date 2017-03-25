---
title: "Функции пространство имен Concurrency::precise_math | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 727bbabf3c3b016e7c2666e3f77cf15b7e36d2a8
ms.lasthandoff: 03/17/2017

---
# <a name="concurrencyprecisemath-namespace-functions"></a>Функции пространство имен Concurrency::precise_math
||||  
|-|-|-|  
|[acos](#acos)|[acosf](#acosf)|[acosh](#acosh)|  
|[acoshf](#acoshf)|[asin](#asin)|[asinf](#asinf)|  
|[asinh](#asinh)|[asinhf](#asinhf)|[atan](#atan)|  
|[atan2](#atan2)|[atan2f](#atan2f)|[atanf](#atanf)|  
|[atanh](#atanh)|[atanhf](#atanhf)|[cbrt](#cbrt)|  
|[cbrtf](#cbrtf)|[ceil](#ceil)|[ceilf](#ceilf)|  
|[copysign](#copysign)|[copysignf](#copysignf)|[cos](#cos)|  
|[cosf](#cosf)|[cosh](#cosh)|[coshf](#coshf)|  
|[cospi](#cospi)|[cospif](#cospif)|[erf](#erf)|  
|[erfc](#erfc)|[erfcf](#erfcf)|[erfcinv](#erfcinv)|  
|[erfcinvf](#erfcinvf)|[erff](#erff)|[erfinv](#erfinv)|  
|[erfinvf](#erfinvf)|[exp](#exp)|[exp10](#exp10)|  
|[exp10f](#exp10f)|[exp2](#exp2)|[exp2f](#exp2f)|  
|[expf](#expf)|[expm1](#expm1)|[expm1f](#expm1f)|  
|[fabs](#fabs)|[fabsf](#fabsf)|[floor](#floor)| 
|[fdim](#fdim)|[fdimf](#fdimf)|| 
|[floorf](#floorf)|[fma](#fma)|[fmaf](#fmaf)|
[fmax](#fmax)|[fmaxf](#fmaxf)|| 
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|  
|[fmodf](#fmodf)|[fpclassify](#fpclassify)|[frexp](#frexp)|  
|[frexpf](#frexpf)|[hypot](#hypot)|[hypotf](#hypotf)|  
|[ilogb](#ilogb)|[ilogbf](#ilogbf)|[isFinite](#isfinite)|  
|[isinf](#isinf)|[isnan](#isnan)|[isnormal](#isnormal)|  
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[lgamma](#lgamma)|  
|[lgammaf](#lgammaf)|[log](#log)|[log10](#log10)|  
|[log10f](#log10f)|[log1p](#log1p)|[log1pf](#log1pf)|  
|[log2](#log2)|[log2f](#log2f)|[logb](#logb)|  
|[logbf](#logbf)|[logf](#logf)|[modf](#modf)|  
|[modff](#modff)|[nan](#nan)|[nanf](#nanf)|  
|[nearbyint](#nearbyint)|[nearbyintf](#nearbyintf)|[nextafter](#nextafter)|  
|[nextafterf](#nextafterf)|[PHI](#phi)|[phif](#phif)|  
|[pow](#pow)|[powf](#powf)|[probit](#probit)|  
|[probitf](#probitf)|[rcbrt](#rcbrt)|[rcbrtf](#rcbrtf)|  
|[remainder](#remainder)|[remainderf](#remainderf)|[remquo](#remquo)|  
|[remquof](#remquof)|[round](#round)|[roundf](#roundf)|  
|[rsqrt](#rsqrt)|[rsqrtf](#rsqrtf)|[scalb](#scalb)|  
|[scalbf](#scalbf)|[scalbn](#scalbn)|[scalbnf](#scalbnf)|  
|[signbit](#signbit)|[signbitf](#signbitf)|[sin](#sin)|  
|[sincos](#sincos)|[sincosf](#sincosf)|[sinf](#sinf)|  
|[sinh](#sinh)|[sinhf](#sinhf)|[sinpi](#sinpi)|  
|[sinpif](#sinpif)|[sqrt](#sqrt)|[sqrtf](#sqrtf)|  
|[tan](#tan)|[tanf](#tanf)|[tanh](#tanh)|  
|[tanhf](#tanhf)|[tanpi](#tanpi)|[tanpif](#tanpif)|  
|[tgamma](#tgamma)|[tgammaf](#tgammaf)|[trunc](#trunc)|  
|[truncf](#truncf)|  
  
##  <a name="acos"></a>  acos  
 Вычисляет арккосинус аргумента  
  
```  
inline float acos(float _X) restrict(amp);

 
inline double acos(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арккосинуса аргумента  
  
##  <a name="acosf"></a>acosf  
 Вычисляет арккосинус аргумента  
  
```  
inline float acosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арккосинуса аргумента  
  
##  <a name="acosh"></a>ACOSH  
 Вычисляет гиперболический арккосинус аргумента  
  
```  
inline float acosh(float _X) restrict(amp);

 
inline double acosh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный гиперболический косинус значение аргумента  
  
##  <a name="acoshf"></a>acoshf  
 Вычисляет гиперболический арккосинус аргумента  
  
```  
inline float acoshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный гиперболический косинус значение аргумента  
  
##  <a name="asin"></a>  asin  
 Вычисляет гиперболический арксинус аргумента  
  
```  
inline float asin(float _X) restrict(amp);

 
inline double asin(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арксинуса аргумента  
  
##  <a name="asinf"></a>asinf  
 Вычисляет гиперболический арксинус аргумента  
  
```  
inline float asinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арксинуса аргумента  
  
##  <a name="asinh"></a>ASINH  
 Вычисляет гиперболический арксинус аргумента  
  
```  
inline float asinh(float _X) restrict(amp);

 
inline double asinh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, гиперболический арксинус аргумента  
  
##  <a name="asinhf"></a>asinhf  
 Вычисляет гиперболический арксинус аргумента  
  
```  
inline float asinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, гиперболический арксинус аргумента  
  
##  <a name="atan"></a>  atan  
 Вычисляет арктангенс аргумента.  
  
```  
inline float atan(float _X) restrict(amp);

 
inline double atan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арктангенса аргумента  
  
##  <a name="atan2"></a>  atan2  
 Вычисляет арктангенс _Y или _X  
  
```  
inline float atan2(
    float _Y,  
    float _X) restrict(amp);

 
inline double atan2(
    double _Y,  
    double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Y`  
 Значение с плавающей запятой  
  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арктангенса _Y или _X  
  
##  <a name="atan2f"></a>atan2f  
 Вычисляет арктангенс _Y или _X  
  
```  
inline float atan2f(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Y`  
 Значение с плавающей запятой  
  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арктангенса _Y или _X  
  
##  <a name="atanf"></a>atanf  
 Вычисляет арктангенс аргумента.  
  
```  
inline float atanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арктангенса аргумента  
  
##  <a name="atanh"></a>ATANH  
 Вычисляет гиперболический арктангенс аргумента  
  
```  
inline float atanh(float _X) restrict(amp);

 
inline double atanh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный гиперболический тангенс значение аргумента  
  
##  <a name="atanhf"></a>atanhf  
 Вычисляет гиперболический арктангенс аргумента  
  
```  
inline float atanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный гиперболический тангенс значение аргумента  
  
##  <a name="cbrt"></a>cbrt  
 Вычисляет кубический корень реальных аргумента  
  
```  
inline float cbrt(float _X) restrict(amp);

 
inline double cbrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реальные кубический корень аргумента  
  
##  <a name="cbrtf"></a>cbrtf  
 Вычисляет кубический корень реальных аргумента  
  
```  
inline float cbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реальные кубический корень аргумента  
  
##  <a name="ceil"></a>ceil  
 Вычисляет ceiling аргумента  
  
```  
inline float ceil(float _X) restrict(amp);

 
inline double ceil(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает максимальную аргумента  
  
##  <a name="ceilf"></a>ceilf  
 Вычисляет ceiling аргумента  
  
```  
inline float ceilf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает максимальную аргумента  
  
##  <a name="copysign"></a>copysign  
 Возвращает значение, указывающее величину _X и знак _Y  
  
```  
inline float copysign(
    float _X,  
    float _Y) restrict(amp);

 
inline double copysign(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение с величина _X и знак _Y  
  
##  <a name="copysignf"></a>copysignf  
 Возвращает значение, указывающее величину _X и знак _Y  
  
```  
inline float copysignf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение с величина _X и знак _Y  
  
##  <a name="cos"></a>  cos  
 Вычисляет косинус аргумента  
  
```  
inline float cos(float _X) restrict(amp);

 
inline double cos(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает косинус значение аргумента  
  
##  <a name="cosf"></a>cosf  
 Вычисляет косинус аргумента  
  
```  
inline float cosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает косинус значение аргумента  
  
##  <a name="cosh"></a>  cosh  
 Вычисляет гиперболический косинус значение аргумента  
  
```  
inline float cosh(float _X) restrict(amp);

 
inline double cosh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает гиперболический косинус значение аргумента  
  
##  <a name="coshf"></a>coshf  
 Вычисляет гиперболический косинус значение аргумента  
  
```  
inline float coshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает гиперболический косинус значение аргумента  
  
##  <a name="cospi"></a>cospi  
 Вычисляет косинус числа пи * _X  
  
```  
inline float cospi(float _X) restrict(amp);

 
inline double cospi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает косинус числа пи * _X  
  
##  <a name="cospif"></a>cospif  
 Вычисляет косинус числа пи * _X  
  
```  
inline float cospif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает косинус числа пи * _X  
  
##  <a name="erf"></a>erf  
 Вычисляет функцию ошибок _X  
  
```  
inline float erf(float _X) restrict(amp);

 
inline double erf(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает функцию ошибки _X  
  
##  <a name="erfc"></a>erfc  
 Вычисляет дополнительную функцию ошибок _X  
  
```  
inline float erfc(float _X) restrict(amp);

 
inline double erfc(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дополнительную функцию ошибок _X  
  
##  <a name="erfcf"></a>erfcf  
 Вычисляет дополнительную функцию ошибок _X  
  
```  
inline float erfcf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дополнительную функцию ошибок _X  
  
##  <a name="erfcinv"></a>erfcinv  
 Вычисляет обратный дополнительную функцию ошибок _X  
  
```  
inline float erfcinv(float _X) restrict(amp);

 
inline double erfcinv(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный дополнительную функцию ошибок _X  
  
##  <a name="erfcinvf"></a>erfcinvf  
 Вычисляет обратный дополнительную функцию ошибок _X  
  
```  
inline float erfcinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный дополнительную функцию ошибок _X  
  
##  <a name="erff"></a>erff  
 Вычисляет функцию ошибок _X  
  
```  
inline float erff(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает функцию ошибки _X  
  
##  <a name="erfinv"></a>erfinv  
 Вычисляет обратный ошибок _X  
  
```  
inline float erfinv(float _X) restrict(amp);

 
inline double erfinv(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает функцию ошибки обратный _X  
  
##  <a name="erfinvf"></a>erfinvf  
 Вычисляет обратный ошибок _X  
  
```  
inline float erfinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает функцию ошибки обратный _X  
  
##  <a name="exp10"></a>exp10  
 Вычисляет экспоненту аргумента base-10  
  
```  
inline float exp10(float _X) restrict(amp);

 
inline double exp10(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента с основанием&10;  
  
##  <a name="exp10f"></a>exp10f  
 Вычисляет экспоненту аргумента base-10  
  
```  
inline float exp10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента с основанием&10;  
  
##  <a name="expm1"></a>expm1  
 Вычисляет экспоненту аргумента с основанием e, за вычетом 1  
  
```  
inline float expm1(float exponent) restrict(amp);

 
inline double expm1(double exponent) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `exponent`  
 Экспоненциальный член *n* математического выражения `e` <sup>n</sup>, где `e` является основанием натурального логарифма.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента с основанием e, за вычетом 1  
  
##  <a name="expm1f"></a>expm1f  
 Вычисляет экспоненту аргумента с основанием e, за вычетом 1  
  
```  
inline float expm1f(float exponent) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `exponent`  
 Экспоненциальный член *n* математического выражения `e` <sup>n</sup>, где `e` является основанием натурального логарифма.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента с основанием e, за вычетом 1  
  
##  <a name="exp"></a>  exp  
 Вычисляет экспоненту аргумента base-e  
  
```  
inline float exp(float _X) restrict(amp);

 
inline double exp(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента с основанием e  
  
##  <a name="expf"></a>expf  
 Вычисляет экспоненту аргумента base-e  
  
```  
inline float expf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента с основанием e  
  
##  <a name="exp2"></a>exp2  
 Вычисляет экспоненту аргумента base-2  
  
```  
inline float exp2(float _X) restrict(amp);

 
inline double exp2(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента base-2  
  
##  <a name="exp2f"></a>exp2f  
 Вычисляет экспоненту аргумента base-2  
  
```  
inline float exp2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента base-2  
  
##  <a name="fabs"></a>fabs  
 Возвращает абсолютное значение аргумента  
  
```  
inline float fabs(float _X) restrict(amp);

 
inline double fabs(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает абсолютное значение аргумента  
  
##  <a name="fabsf"></a>fabsf  
 Возвращает абсолютное значение аргумента  
  
```  
inline float fabsf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает абсолютное значение аргумента  

## <a name="fdim"></a>fdim  
Вычисляет положительной разнице между аргументами.
```  
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
`_X`Значение с плавающей запятой `_Y` значение с плавающей запятой


### <a name="return-value"></a>Возвращаемое значение
Разница между _X и _Y Если _X больше _Y; в противном случае, +&0;.
 
## <a name="fdimf"></a>fdimf  
Вычисляет положительной разнице между аргументами.
```
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```
### <a name="parameters"></a>Параметры
`_X`Значение с плавающей запятой `_Y` значение с плавающей запятой

### <a name="return-value"></a>Возвращаемое значение
Разница между _X и _Y Если _X больше _Y; в противном случае, +&0;. 
  
##  <a name="floor"></a>функция FLOOR  
 Вычисляет floor аргумента  
  
```  
inline float floor(float _X) restrict(amp);

 
inline double floor(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минимальную аргумента  
  
##  <a name="floorf"></a>floorf  
 Вычисляет floor аргумента  
  
```  
inline float floorf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минимальную аргумента  

## <a name="a-namefma-fma"></a><a name="fma">FMA  
Вычисляет произведение первого и второго заданных аргументов, а затем добавляет третий аргумент, указанный для результата; все вычисления в одну операцию.
```
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
`_X`Первый аргумент с плавающей запятой.
`_Y`Второй аргумент с плавающей запятой.
`_Z`Третий аргумент с плавающей запятой.

### <a name="return-value"></a>Возвращаемое значение
Результат выражения (_X * _Y) + _Z. Все вычисления в одной операции. то есть, вложенных выражений вычисляются бесконечный точности, и лишь финальный результат округляется. 

## <a name="fmaf"></a>fmaf  
Вычисляет произведение первого и второго заданных аргументов, а затем добавляет третий аргумент, указанный для результата; все вычисления в одну операцию.
```
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```  
### <a name="parameters"></a>Параметры
`_X`Первый аргумент с плавающей запятой.
`_Y`Второй аргумент с плавающей запятой.
`_Z`Третий аргумент с плавающей запятой.

### <a name="return-value"></a>Возвращаемое значение
Результат выражения (_X * _Y) + _Z. Все вычисления в одной операции. то есть, вложенных выражений вычисляются бесконечный точности, и лишь финальный результат округляется.
  
##  <a name="fmax"></a>fmax  
 Определите максимальное числовое значение аргументов  
  
```  
inline float fmax(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmax(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает максимальное значение числового аргументов  
  
##  <a name="fmaxf"></a>fmaxf  
 Определите максимальное числовое значение аргументов  
  
```  
inline float fmaxf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает максимальное значение числового аргументов  
  
##  <a name="fmin"></a>fmin  
 Определите минимальное числовое значение аргументов  
  
```  
inline float fmin(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmin(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минимальное значение числового аргументов  
  
##  <a name="fminf"></a>fminf  
 Определите минимальное числовое значение аргументов  
  
```  
inline float fminf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минимальное значение числового аргументов  
  
##  <a name="fmod"></a>Функция fmod (C++ AMP)  
 Вычисляет остаток от первого указанного аргумента деленное второго заданного аргумента.  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);

 
inline double fmod(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Первый аргумент с плавающей запятой.  
  
 `_Y`  
 Второй аргумент с плавающей запятой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В оставшейся части `_X` деленное `_Y`; то есть, значение `_X`  -  `_Y` *n*, где *n* является целым числом таким образом, что величина `_X`  -  `_Y` *n* меньше, чем абсолютное значение `_Y`.  
  
##  <a name="fmodf"></a>fmodf  
 Вычисляет остаток от первого указанного аргумента деленное второго заданного аргумента.  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Первый аргумент с плавающей запятой.  
  
 `_Y`  
 Второй аргумент с плавающей запятой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В оставшейся части `_X` деленное `_Y`; то есть, значение `_X`  -  `_Y` *n*, где *n* является целым числом таким образом, что величина `_X`  -  `_Y` *n* меньше, чем абсолютное значение `_Y`.  
  
##  <a name="fpclassify"></a>fpclassify  
 Классифицирует значение аргумента как нулевое значение NaN, бесконечное, обычная, subnormal,  
  
```  
inline int fpclassify(float _X) restrict(amp);

 
inline int fpclassify(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение числа макроса классификации соответствующие значению аргумента.  
  
##  <a name="frexp"></a>frexp  
 Возвращает мантиссы и экспоненты _X  
  
```  
inline float frexp(
    float _X,  
    _Out_ int* _Exp) restrict(amp);

 
inline double frexp(
    double _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Exp`  
 Возвращает порядок _X целое число со знаком в значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X мантиссы  
  
##  <a name="frexpf"></a>frexpf  
 Возвращает мантиссы и экспоненты _X  
  
```  
inline float frexpf(
    float _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Exp`  
 Возвращает порядок _X целое число со знаком в значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X мантиссы  
  
##  <a name="hypot"></a>hypot  
 Вычисляет квадратный корень из суммы квадратов _X и _Y  
  
```  
inline float hypot(
    float _X,  
    float _Y) restrict(amp);

 
inline double hypot(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает квадратный корень из суммы квадратов _X и _Y  
  
##  <a name="hypotf"></a>hypotf  
 Вычисляет квадратный корень из суммы квадратов _X и _Y  
  
```  
inline float hypotf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает квадратный корень из суммы квадратов _X и _Y  
  
##  <a name="ilogb"></a>ilogb  
 Извлеките экспоненты _X как значение типа int со знаком  
  
```  
inline int ilogb(float _X) restrict(amp);

 
inline int ilogb(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение экспоненты _X как значение типа int со знаком  
  
##  <a name="ilogbf"></a>ilogbf  
 Извлеките экспоненты _X как значение типа int со знаком  
  
```  
inline int ilogbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение экспоненты _X как значение типа int со знаком  
  
##  <a name="isfinite"></a>isFinite  
 Определяет, имеет ли аргумент конечное значение  
  
```  
inline int isfinite(float _X) restrict(amp);

 
inline int isfinite(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение только в том случае, если аргумент имеет конечное значение  
  
##  <a name="isinf"></a>isinf  
 Определяет, является ли аргумент бесконечности  
  
```  
inline int isinf(float _X) restrict(amp);

 
inline int isinf(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение только в том случае, если аргумент имеет бесконечное значение  
  
##  <a name="isnan"></a>isNaN  
 Определяет, является ли аргумент значение NaN  
  
```  
inline int isnan(float _X) restrict(amp);

 
inline int isnan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение только в том случае, если аргумент имеет значение NaN  
  
##  <a name="isnormal"></a>isnormal  
 Определяет, является ли аргумент норм.  
  
```  
inline int isnormal(float _X) restrict(amp);

 
inline int isnormal(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение только в том случае, если аргумент имеет значение normal  
  
##  <a name="ldexp"></a>ldexp  
 Вычисляет действительное число из указанного мантисса и степень.  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);

 
inline double ldexp(
    double _X,  
    double _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой, мантиссы  
  
 `_Exp`  
 Целочисленное значение, показатель степени  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X * 2 ^ _Exp  
  
##  <a name="ldexpf"></a>ldexpf  
 Вычисляет действительное число из указанного мантисса и степень.  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой, мантиссы  
  
 `_Exp`  
 Целочисленное значение, показатель степени  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X * 2 ^ _Exp  
  
##  <a name="lgamma"></a>lgamma  
 Вычисляет натуральный логарифм гамма аргумента абсолютное значение  
  
```  
inline float lgamma(
    float _X,  
    _Out_ int* _Sign) restrict(amp);

 
inline double lgamma(
    double _X,  
    _Out_ int* _Sign) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Sign`  
 Возвращает знак  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает натуральный логарифм гамма аргумента абсолютное значение  
  
##  <a name="lgammaf"></a>lgammaf  
 Вычисляет натуральный логарифм гамма аргумента абсолютное значение  
  
```  
inline float lgammaf(
    float _X,  
    _Out_ int* _Sign) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Sign`  
 Возвращает знак  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает натуральный логарифм гамма аргумента абсолютное значение  
  
##  <a name="log"></a>  log  
 Вычисляет логарифм аргумента  
  
```  
inline float log(float _X) restrict(amp);

 
inline double log(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает логарифм с основанием e аргумента  
  
##  <a name="log10"></a>  log10  
 Вычисляет логарифм по основанию&10; аргумента  
  
```  
inline float log10(float _X) restrict(amp);

 
inline double log10(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает десятичный логарифм аргумента  
  
##  <a name="log10f"></a>log10f  
 Вычисляет логарифм по основанию&10; аргумента  
  
```  
inline float log10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает десятичный логарифм аргумента  
  
##  <a name="log1p"></a>log1p  
 Вычисляет логарифм с основанием e 1, а также аргумент  
  
```  
inline float log1p(float _X) restrict(amp);

 
inline double log1p(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает логарифм с основанием e 1, а также аргумент  
  
##  <a name="log1pf"></a>log1pf  
 Вычисляет логарифм с основанием e 1, а также аргумент  
  
```  
inline float log1pf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает логарифм с основанием e 1, а также аргумент  
  
##  <a name="log2"></a>LOG2  
 Вычисляет логарифм по основанию&2; аргумента  
  
```  
inline float log2(float _X) restrict(amp);

 
inline double log2(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает десятичный логарифм аргумента  
  
##  <a name="log2f"></a>log2f  
 Вычисляет логарифм по основанию&2; аргумента  
  
```  
inline float log2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает десятичный логарифм аргумента  
  
##  <a name="logb"></a>logb  
 Извлекает экспоненты _X, как значение целого числа со знаком в формате с плавающей запятой  
  
```  
inline float logb(float _X) restrict(amp);

 
inline double logb(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение со знаком экспоненты _X  
  
##  <a name="logbf"></a>logbf  
 Извлекает экспоненты _X, как значение целого числа со знаком в формате с плавающей запятой  
  
```  
inline float logbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение со знаком экспоненты _X  
  
##  <a name="logf"></a>logf  
 Вычисляет логарифм аргумента  
  
```  
inline float logf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает логарифм с основанием e аргумента  
  
##  <a name="modf"></a>modf  
 Разделяет указанный аргумент в долях и целое число частей.  
  
```  
inline float modf(
    float _X,  
    _Out_ float* _Iptr) restrict(amp);

 
inline double modf(
    double _X,  
    _Out_ double* _Iptr) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Iptr`(выходной параметр)  
 Целочисленная часть `_X`, как значение с плавающей запятой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Подписанные дробной части числа `_X`.  
  
##  <a name="modff"></a>modff  
 Разделяет указанный аргумент в долях и целое число частей.  
  
```  
inline float modff(
    float _X,  
    _Out_ float* _Iptr) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Iptr`  
 Целочисленная часть `_X`, как значение с плавающей запятой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает подписанный дробной части числа `_X`.  
  
##  <a name="nan"></a>NaN  
 Возвращает тихий NaN  
  
```  
inline double nan(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает несигнальным значением NaN, если в _X указано, доступные с содержимым  
  
##  <a name="nanf"></a>nanf  
 Возвращает тихий NaN  
  
```  
inline float nanf(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает несигнальным значением NaN, если в _X указано, доступные с содержимым  
  
##  <a name="nearbyint"></a>nearbyint  
 Округляет аргумент целочисленного значения в формате с плавающей запятой, используя текущее направление округления.  
  
```  
inline float nearbyint(float _X) restrict(amp);

 
inline double nearbyint(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает округленное целочисленное значение.  
  
##  <a name="nearbyintf"></a>nearbyintf  
 Округляет аргумент целочисленного значения в формате с плавающей запятой, используя текущее направление округления.  
  
```  
inline float nearbyintf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает округленное целочисленное значение.  
  
##  <a name="nextafter"></a>nextafter  
 Определить Далее представимым значением типа функции, после _X в направлении _Y  
  
```  
inline float nextafter(
    float _X,  
    float _Y) restrict(amp);

 
inline double nextafter(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тип функции, далее представимым значением после _X в направлении _Y  
  
##  <a name="nextafterf"></a>nextafterf  
 Определить Далее представимым значением типа функции, после _X в направлении _Y  
  
```  
inline float nextafterf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тип функции, далее представимым значением после _X в направлении _Y  
  
##  <a name="phi"></a>PHI  
 Возвращает интегральную функцию распределения аргумента  
  
```  
inline float phi(float _X) restrict(amp);

 
inline double phi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает интегральную функцию распределения аргумента  
  
##  <a name="phif"></a>phif  
 Возвращает интегральную функцию распределения аргумента  
  
```  
inline float phif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает интегральную функцию распределения аргумента  
  
##  <a name="pow"></a>  pow  
 Вычисляет _X, возведенное в степень _Y  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);

 
inline double pow(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой, базовый  
  
 `_Y`  
 Значение с плавающей запятой, показатель степени  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="powf"></a>powf  
 Вычисляет _X, возведенное в степень _Y  
  
```  
inline float powf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой, базовый  
  
 `_Y`  
 Значение с плавающей запятой, показатель степени  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="probit"></a>probit  
 Возвращает обратный интегральную функцию распределения аргумента  
  
```  
inline float probit(float _X) restrict(amp);

 
inline double probit(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный интегральную функцию распределения аргумента  
  
##  <a name="probitf"></a>probitf  
 Возвращает обратный интегральную функцию распределения аргумента  
  
```  
inline float probitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный интегральную функцию распределения аргумента  
  
##  <a name="rcbrt"></a>rcbrt  
 Возвращает обратное кубический корень аргумента  
  
```  
inline float rcbrt(float _X) restrict(amp);

 
inline double rcbrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратное кубический корень аргумента  
  
##  <a name="rcbrtf"></a>rcbrtf  
 Возвращает обратное кубический корень аргумента  
  
```  
inline float rcbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратное кубический корень аргумента  
  
##  <a name="remainder"></a>Остаток  
 Вычисляет остаток: _X REM _Y  
  
```  
inline float remainder(
    float _X,  
    float _Y) restrict(amp);

 
inline double remainder(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X REM _Y  
  
##  <a name="remainderf"></a>remainderf  
 Вычисляет остаток: _X REM _Y  
  
```  
inline float remainderf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X REM _Y  
  
##  <a name="remquo"></a>remquo  
 Вычисляет остаток от первого указанного аргумента деленное второго заданного аргумента. Также вычисляет частное мантиссой первого указанного аргумента деленное мантиссой второго заданного аргумента и возвращает частное, используя расположении, заданном в качестве третьего аргумента.  
  
```  
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
 `_X`  
 Первый аргумент с плавающей запятой.  
  
 `_Y`  
 Второй аргумент с плавающей запятой.  
  
 `_Quo`(выходной параметр)  
 Адрес целое число, используется для возвращения частное дробной части `_X` деленное дробной части `_Y`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает остаток от `_X` деленное `_Y`.  
  
##  <a name="remquof"></a>remquof  
 Вычисляет остаток от первого указанного аргумента деленное второго заданного аргумента. Также вычисляет частное мантиссой первого указанного аргумента деленное мантиссой второго заданного аргумента и возвращает частное, используя расположении, заданном в качестве третьего аргумента.  
  
```  
inline float remquof(
    float _X,  
    float _Y,  
    _Out_ int* _Quo) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Первый аргумент с плавающей запятой.  
  
 `_Y`  
 Второй аргумент с плавающей запятой.  
  
 `_Quo`(выходной параметр)  
 Адрес целое число, используется для возвращения частное дробной части `_X` деленное дробной части `_Y`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает остаток от `_X` деленное `_Y`.  
  
##  <a name="round"></a>Округление  
 Округляет _X до ближайшего целого числа  
  
```  
inline float round(float _X) restrict(amp);

 
inline double round(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает целое число, ближайшее из _X  
  
##  <a name="roundf"></a>roundf  
 Округляет _X до ближайшего целого числа  
  
```  
inline float roundf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает целое число, ближайшее из _X  
  
##  <a name="rsqrt"></a>rsqrt  
 Возвращает обратное квадратного корня аргумент  
  
```  
inline float rsqrt(float _X) restrict(amp);

 
inline double rsqrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратное квадратного корня аргумент  
  
##  <a name="rsqrtf"></a>rsqrtf  
 Возвращает обратное квадратного корня аргумент  
  
```  
inline float rsqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратное квадратного корня аргумент  
  
##  <a name="scalb"></a>scalb  
 Умножает _X константой FLT_RADIX для _Y питания  
  
```  
inline float scalb(
    float _X,  
    float _Y) restrict(amp);

 
inline double scalb(
    double _X,  
    double _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X * (FLT_RADIX ^ _Y)  
  
##  <a name="scalbf"></a>scalbf  
 Умножает _X константой FLT_RADIX для _Y питания  
  
```  
inline float scalbf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X * (FLT_RADIX ^ _Y)  
  
##  <a name="scalbn"></a>scalbn  
 Умножает _X константой FLT_RADIX для _Y питания  
  
```  
inline float scalbn(
    float _X,  
    int _Y) restrict(amp);

 
inline double scalbn(
    double _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X * (FLT_RADIX ^ _Y)  
  
##  <a name="scalbnf"></a>scalbnf  
 Умножает _X константой FLT_RADIX для _Y питания  
  
```  
inline float scalbnf(
    float _X,  
    int _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X * (FLT_RADIX ^ _Y)  
  
##  <a name="signbit"></a>signbit  
 Определяет, является ли знак _X отрицательное  
  
```  
inline int signbit(float _X) restrict(amp);

 
inline int signbit(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение только в том случае, если знак _X отрицательна  
  
##  <a name="signbitf"></a>signbitf  
 Определяет, является ли знак _X отрицательное  
  
```  
inline int signbitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение только в том случае, если знак _X отрицательна  
  
##  <a name="sin"></a>  sin  
 Вычисляет синус аргумента  
  
```  
inline float sin(float _X) restrict(amp);

 
inline double sin(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает синус аргумента  
  
##  <a name="sinf"></a>sinf  
 Вычисляет синус аргумента  
  
```  
inline float sinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает синус аргумента  
  
##  <a name="sincos"></a>sincos  
 Вычисляет синус и косинус значение _X  
  
```  
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
 `_X`  
 Значение с плавающей запятой  
  
 `_S`  
 Возвращает синус _X  
  
 `_C`  
 Возвращает косинус числа _X  
  
##  <a name="sincosf"></a>sincosf  
 Вычисляет синус и косинус значение _X  
  
```  
inline void sincosf(
    float _X,  
    _Out_ float* _S,  
    _Out_ float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_S`  
 Возвращает синус _X  
  
 `_C`  
 Возвращает косинус числа _X  
  
##  <a name="sinh"></a>  sinh  
 Вычисляет гиперболический синус значение аргумента  
  
```  
inline float sinh(float _X) restrict(amp);

 
inline double sinh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает гиперболический синус значение аргумента  
  
##  <a name="sinhf"></a>sinhf  
 Вычисляет гиперболический синус значение аргумента  
  
```  
inline float sinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает гиперболический синус значение аргумента  
  
##  <a name="sinpi"></a>sinpi  
 Вычисляет синус числа пи * _X  
  
```  
inline float sinpi(float _X) restrict(amp);

 
inline double sinpi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает синус числа пи * _X  
  
##  <a name="sinpif"></a>sinpif  
 Вычисляет синус числа пи * _X  
  
```  
inline float sinpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает синус числа пи * _X  
  
##  <a name="sqrt"></a>  sqrt  
 Вычисляет корень squre аргумента  
  
```  
inline float sqrt(float _X) restrict(amp);

 
inline double sqrt(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает корень squre аргумента  
  
##  <a name="sqrtf"></a>sqrtf  
 Вычисляет корень squre аргумента  
  
```  
inline float sqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает корень squre аргумента  
  
##  <a name="tan"></a>  tan  
 Вычисляет тангенс значение аргумента  
  
```  
inline float tan(float _X) restrict(amp);

 
inline double tan(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тангенс значение аргумента  
  
##  <a name="tanf"></a>tanf  
 Вычисляет тангенс значение аргумента  
  
```  
inline float tanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тангенс значение аргумента  
  
##  <a name="tanh"></a>  tanh  
 Вычисляет гиперболический тангенс значение аргумента  
  
```  
inline float tanh(float _X) restrict(amp);

 
inline double tanh(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает гиперболический тангенс значение аргумента  
  
##  <a name="tanhf"></a>tanhf  
 Вычисляет гиперболический тангенс значение аргумента  
  
```  
inline float tanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает гиперболический тангенс значение аргумента  
  
##  <a name="tanpi"></a>tanpi  
 Вычисляет тангенс числа пи * _X  
  
```  
inline float tanpi(float _X) restrict(amp);

 
inline double tanpi(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тангенс числа пи * _X  
  
##  <a name="tanpif"></a>tanpif  
 Вычисляет тангенс числа пи * _X  
  
```  
inline float tanpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тангенс числа пи * _X  
  
##  <a name="tgamma"></a>tgamma  
 Вычисляет гамма-функции _X  
  
```  
inline float tgamma(float _X) restrict(amp);

 
inline double tgamma(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение гамма-функции из _X  
  
##  <a name="tgammaf"></a>tgammaf  
 Вычисляет гамма-функции _X  
  
```  
inline float tgammaf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение гамма-функции из _X  
  
##  <a name="trunc"></a>TRUNC  
 Усекает для целочисленный аргумент  
  
```  
inline float trunc(float _X) restrict(amp);

 
inline double trunc(double _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает целочисленный аргумент  
  
##  <a name="truncf"></a>truncf  
 Усекает для целочисленный аргумент  
  
```  
inline float truncf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает целочисленный аргумент  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::precise_math](concurrency-precise-math-namespace.md)

