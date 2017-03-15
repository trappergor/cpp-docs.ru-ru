---
title: "Функции пространство имен Concurrency::precise_math | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 73273a58f73860c77810a6ab59def560962f9539
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyprecisemath-namespace-functions"></a>Функции пространство имен Concurrency::precise_math
||||  
|-|-|-|  
|[Функция ACOS](#acos)|[Функция acosf](#acosf)|[Функция ACOSH](#acosh)|  
|[Функция acoshf](#acoshf)|[Функция ASIN](#asin)|[Функция asinf](#asinf)|  
|[Функция ASINH](#asinh)|[Функция asinhf](#asinhf)|[Функция ATAN](#atan)|  
|[Функция ATAN2](#atan2)|[Функция atan2f](#atan2f)|[Функция atanf](#atanf)|  
|[Функция ATANH](#atanh)|[Функция atanhf](#atanhf)|[Функция cbrt](#cbrt)|  
|[Функция cbrtf](#cbrtf)|[Функция ceil](#ceil)|[Функция ceilf](#ceilf)|  
|[Функция copysign](#copysign)|[Функция copysignf](#copysignf)|[cos функции](#cos)|  
|[Функция cosf](#cosf)|[Функция COSH](#cosh)|[Функция coshf](#coshf)|  
|[Функция cospi](#cospi)|[Функция cospif](#cospif)|[Функция erf](#erf)|  
|[Функция erfc](#erfc)|[Функция erfcf](#erfcf)|[Функция erfcinv](#erfcinv)|  
|[Функция erfcinvf](#erfcinvf)|[Функция erff](#erff)|[Функция erfinv](#erfinv)|  
|[Функция erfinvf](#erfinvf)|[Функция EXP](#exp)|[Функция exp10](#exp10)|  
|[Функция exp10f](#exp10f)|[Функция exp2](#exp2)|[Функция exp2f](#exp2f)|  
|[Функция expf](#expf)|[Функция expm1](#expm1)|[Функция expm1f](#expm1f)|  
|[Функция fabs](#fabs)|[Функция fabsf](#fabsf)|[Функция FLOOR](#floor)| 
|[Функция fdim](#fdim)|[Функция fdimf](#fdimf)|| 
|[Функция floorf](#floorf)|[Функция FMA](#fma)|[Функция fmaf](#fmaf)|
[Функция fmax](#fmax)|[Функция fmaxf](#fmaxf)|| 
|[Функция fmin](#fmin)|[Функция fminf](#fminf)|[Функция fmod](#fmod)|  
|[Функция fmodf](#fmodf)|[Функция fpclassify](#fpclassify)|[Функция frexp](#frexp)|  
|[Функция frexpf](#frexpf)|[Функция hypot](#hypot)|[Функция hypotf](#hypotf)|  
|[Функция ilogb](#ilogb)|[Функция ilogbf](#ilogbf)|[Функция isFinite](#isfinite)|  
|[Функция isinf](#isinf)|[Функция isNaN](#isnan)|[Функция isnormal](#isnormal)|  
|[Функция ldexp](#ldexp)|[Функция ldexpf](#ldexpf)|[Функция lgamma](#lgamma)|  
|[Функция lgammaf](#lgammaf)|[Функция log](#log)|[Функция LOG10](#log10)|  
|[Функция log10f](#log10f)|[Функция log1p](#log1p)|[Функция log1pf](#log1pf)|  
|[Функция log2](#log2)|[Функция log2f](#log2f)|[Функция logb](#logb)|  
|[Функция logbf](#logbf)|[Функция logf](#logf)|[Функция modf](#modf)|  
|[Функция modff](#modff)|[NaN-функция](#nan)|[Функция nanf](#nanf)|  
|[Функция nearbyint](#nearbyint)|[Функция nearbyintf](#nearbyintf)|[Функция nextafter](#nextafter)|  
|[Функция nextafterf](#nextafterf)|[Функция PHI](#phi)|[Функция phif](#phif)|  
|[Функция pow](#pow)|[Функция powf](#powf)|[Функция probit](#probit)|  
|[Функция probitf](#probitf)|[Функция rcbrt](#rcbrt)|[Функция rcbrtf](#rcbrtf)|  
|[Функция Remainder](#remainder)|[Функция remainderf](#remainderf)|[Функция remquo](#remquo)|  
|[Функция remquof](#remquof)|[Функция Round](#round)|[Функция roundf](#roundf)|  
|[Функция rsqrt](#rsqrt)|[Функция rsqrtf](#rsqrtf)|[Функция scalb](#scalb)|  
|[Функция scalbf](#scalbf)|[Функция scalbn](#scalbn)|[Функция scalbnf](#scalbnf)|  
|[Функция signbit](#signbit)|[Функция signbitf](#signbitf)|[Функция sin](#sin)|  
|[Функция sincos](#sincos)|[Функция sincosf](#sincosf)|[Функция sinf](#sinf)|  
|[Функция SINH](#sinh)|[Функция sinhf](#sinhf)|[Функция sinpi](#sinpi)|  
|[Функция sinpif](#sinpif)|[Функция SQRT](#sqrt)|[Функция sqrtf](#sqrtf)|  
|[Функция tan](#tan)|[Функция tanf](#tanf)|[Функция TANH](#tanh)|  
|[Функция tanhf](#tanhf)|[Функция tanpi](#tanpi)|[Функция tanpif](#tanpif)|  
|[Функция tgamma](#tgamma)|[Функция tgammaf](#tgammaf)|[Функция TRUNC](#trunc)|  
|[Функция truncf](#truncf)|  
  
##  <a name="a-nameacosa--acos-function"></a><a name="acos"></a>Функция ACOS  
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
  
##  <a name="a-nameacosfa--acosf-function"></a><a name="acosf"></a>Функция acosf  
 Вычисляет арккосинус аргумента  
  
```  
inline float acosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арккосинуса аргумента  
  
##  <a name="a-nameacosha--acosh-function"></a><a name="acosh"></a>Функция ACOSH  
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
  
##  <a name="a-nameacoshfa--acoshf-function"></a><a name="acoshf"></a>Функция acoshf  
 Вычисляет гиперболический арккосинус аргумента  
  
```  
inline float acoshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный гиперболический косинус значение аргумента  
  
##  <a name="a-nameasina--asin-function"></a><a name="asin"></a>Функция ASIN  
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
  
##  <a name="a-nameasinfa--asinf-function"></a><a name="asinf"></a>Функция asinf  
 Вычисляет гиперболический арксинус аргумента  
  
```  
inline float asinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арксинуса аргумента  
  
##  <a name="a-nameasinha--asinh-function"></a><a name="asinh"></a>Функция ASINH  
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
  
##  <a name="a-nameasinhfa--asinhf-function"></a><a name="asinhf"></a>Функция asinhf  
 Вычисляет гиперболический арксинус аргумента  
  
```  
inline float asinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, гиперболический арксинус аргумента  
  
##  <a name="a-nameatana--atan-function"></a><a name="atan"></a>Функция ATAN  
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
  
##  <a name="a-nameatan2a--atan2-function"></a><a name="atan2"></a>Функция ATAN2  
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
  
##  <a name="a-nameatan2fa--atan2f-function"></a><a name="atan2f"></a>Функция atan2f  
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
  
##  <a name="a-nameatanfa--atanf-function"></a><a name="atanf"></a>Функция atanf  
 Вычисляет арктангенс аргумента.  
  
```  
inline float atanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение арктангенса аргумента  
  
##  <a name="a-nameatanha--atanh-function"></a><a name="atanh"></a>Функция ATANH  
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
  
##  <a name="a-nameatanhfa--atanhf-function"></a><a name="atanhf"></a>Функция atanhf  
 Вычисляет гиперболический арктангенс аргумента  
  
```  
inline float atanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный гиперболический тангенс значение аргумента  
  
##  <a name="a-namecbrta--cbrt-function"></a><a name="cbrt"></a>Функция cbrt  
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
  
##  <a name="a-namecbrtfa--cbrtf-function"></a><a name="cbrtf"></a>Функция cbrtf  
 Вычисляет кубический корень реальных аргумента  
  
```  
inline float cbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реальные кубический корень аргумента  
  
##  <a name="a-nameceila--ceil-function"></a><a name="ceil"></a>Функция ceil  
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
  
##  <a name="a-nameceilfa--ceilf-function"></a><a name="ceilf"></a>Функция ceilf  
 Вычисляет ceiling аргумента  
  
```  
inline float ceilf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает максимальную аргумента  
  
##  <a name="a-namecopysigna--copysign-function"></a><a name="copysign"></a>Функция copysign  
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
  
##  <a name="a-namecopysignfa--copysignf-function"></a><a name="copysignf"></a>Функция copysignf  
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
  
##  <a name="a-namecosa--cos-function"></a><a name="cos"></a>cos функции  
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
  
##  <a name="a-namecosfa--cosf-function"></a><a name="cosf"></a>Функция cosf  
 Вычисляет косинус аргумента  
  
```  
inline float cosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает косинус значение аргумента  
  
##  <a name="a-namecosha--cosh-function"></a><a name="cosh"></a>Функция COSH  
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
  
##  <a name="a-namecoshfa--coshf-function"></a><a name="coshf"></a>Функция coshf  
 Вычисляет гиперболический косинус значение аргумента  
  
```  
inline float coshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает гиперболический косинус значение аргумента  
  
##  <a name="a-namecospia--cospi-function"></a><a name="cospi"></a>Функция cospi  
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
  
##  <a name="a-namecospifa--cospif-function"></a><a name="cospif"></a>Функция cospif  
 Вычисляет косинус числа пи * _X  
  
```  
inline float cospif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает косинус числа пи * _X  
  
##  <a name="a-nameerfa--erf-function"></a><a name="erf"></a>Функция erf  
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
  
##  <a name="a-nameerfca--erfc-function"></a><a name="erfc"></a>Функция erfc  
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
  
##  <a name="a-nameerfcfa--erfcf-function"></a><a name="erfcf"></a>Функция erfcf  
 Вычисляет дополнительную функцию ошибок _X  
  
```  
inline float erfcf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дополнительную функцию ошибок _X  
  
##  <a name="a-nameerfcinva--erfcinv-function"></a><a name="erfcinv"></a>Функция erfcinv  
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
  
##  <a name="a-nameerfcinvfa--erfcinvf-function"></a><a name="erfcinvf"></a>Функция erfcinvf  
 Вычисляет обратный дополнительную функцию ошибок _X  
  
```  
inline float erfcinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный дополнительную функцию ошибок _X  
  
##  <a name="a-nameerffa--erff-function"></a><a name="erff"></a>Функция erff  
 Вычисляет функцию ошибок _X  
  
```  
inline float erff(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает функцию ошибки _X  
  
##  <a name="a-nameerfinva--erfinv-function"></a><a name="erfinv"></a>Функция erfinv  
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
  
##  <a name="a-nameerfinvfa--erfinvf-function"></a><a name="erfinvf"></a>Функция erfinvf  
 Вычисляет обратный ошибок _X  
  
```  
inline float erfinvf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает функцию ошибки обратный _X  
  
##  <a name="a-nameexp10a--exp10-function"></a><a name="exp10"></a>Функция exp10  
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
  
##  <a name="a-nameexp10fa--exp10f-function"></a><a name="exp10f"></a>Функция exp10f  
 Вычисляет экспоненту аргумента base-10  
  
```  
inline float exp10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента с основанием&10;  
  
##  <a name="a-nameexpm1a--expm1-function"></a><a name="expm1"></a>Функция expm1  
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
  
##  <a name="a-nameexpm1fa--expm1f-function"></a><a name="expm1f"></a>Функция expm1f  
 Вычисляет экспоненту аргумента с основанием e, за вычетом 1  
  
```  
inline float expm1f(float exponent) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `exponent`  
 Экспоненциальный член *n* математического выражения `e` <sup>n</sup>, где `e` является основанием натурального логарифма.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента с основанием e, за вычетом 1  
  
##  <a name="a-nameexpa--exp-function"></a><a name="exp"></a>Функция EXP  
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
  
##  <a name="a-nameexpfa--expf-function"></a><a name="expf"></a>Функция expf  
 Вычисляет экспоненту аргумента base-e  
  
```  
inline float expf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента с основанием e  
  
##  <a name="a-nameexp2a--exp2-function"></a><a name="exp2"></a>Функция exp2  
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
  
##  <a name="a-nameexp2fa--exp2f-function"></a><a name="exp2f"></a>Функция exp2f  
 Вычисляет экспоненту аргумента base-2  
  
```  
inline float exp2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает экспоненту аргумента base-2  
  
##  <a name="a-namefabsa--fabs-function"></a><a name="fabs"></a>Функция fabs  
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
  
##  <a name="a-namefabsfa--fabsf-function"></a><a name="fabsf"></a>Функция fabsf  
 Возвращает абсолютное значение аргумента  
  
```  
inline float fabsf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает абсолютное значение аргумента  

## <a name="a-namefdima-fdim-function"></a><a name="fdim"></a>Функция fdim  
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
 
## <a name="a-namefdimfa-fdimf-function"></a><a name="fdimf"></a>Функция fdimf
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
  
##  <a name="a-namefloora--floor-function"></a><a name="floor"></a>Функция FLOOR  
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
  
##  <a name="a-namefloorfa--floorf-function"></a><a name="floorf"></a>Функция floorf  
 Вычисляет floor аргумента  
  
```  
inline float floorf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минимальную аргумента  

## <a name="a-namefma-fma-function"></a><a name="fma">Функция FMA  
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

## <a name="a-namefmafa-fmaf-function"></a><a name="fmaf"></a>Функция fmaf  
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
  
##  <a name="a-namefmaxa--fmax-function"></a><a name="fmax"></a>Функция fmax  
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
  
##  <a name="a-namefmaxfa--fmaxf-function"></a><a name="fmaxf"></a>Функция fmaxf  
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
  
##  <a name="a-namefmina--fmin-function"></a><a name="fmin"></a>Функция fmin  
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
  
##  <a name="a-namefminfa--fminf-function"></a><a name="fminf"></a>Функция fminf  
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
  
##  <a name="a-namefmoda--fmod-function-c-amp"></a><a name="fmod"></a>Функция fmod (C++ AMP)  
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
  
##  <a name="a-namefmodfa--fmodf-function"></a><a name="fmodf"></a>Функция fmodf  
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
  
##  <a name="a-namefpclassifya--fpclassify-function"></a><a name="fpclassify"></a>Функция fpclassify  
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
  
##  <a name="a-namefrexpa--frexp-function"></a><a name="frexp"></a>Функция frexp  
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
  
##  <a name="a-namefrexpfa--frexpf-function"></a><a name="frexpf"></a>Функция frexpf  
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
  
##  <a name="a-namehypota--hypot-function"></a><a name="hypot"></a>Функция hypot  
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
  
##  <a name="a-namehypotfa--hypotf-function"></a><a name="hypotf"></a>Функция hypotf  
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
  
##  <a name="a-nameilogba--ilogb-function"></a><a name="ilogb"></a>Функция ilogb  
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
  
##  <a name="a-nameilogbfa--ilogbf-function"></a><a name="ilogbf"></a>Функция ilogbf  
 Извлеките экспоненты _X как значение типа int со знаком  
  
```  
inline int ilogbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение экспоненты _X как значение типа int со знаком  
  
##  <a name="a-nameisfinitea--isfinite-function"></a><a name="isfinite"></a>Функция isFinite  
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
  
##  <a name="a-nameisinfa--isinf-function"></a><a name="isinf"></a>Функция isinf  
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
  
##  <a name="a-nameisnana--isnan-function"></a><a name="isnan"></a>Функция isNaN  
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
  
##  <a name="a-nameisnormala--isnormal-function"></a><a name="isnormal"></a>Функция isnormal  
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
  
##  <a name="a-nameldexpa--ldexp-function"></a><a name="ldexp"></a>Функция ldexp  
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
  
##  <a name="a-nameldexpfa--ldexpf-function"></a><a name="ldexpf"></a>Функция ldexpf  
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
  
##  <a name="a-namelgammaa--lgamma-function"></a><a name="lgamma"></a>Функция lgamma  
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
  
##  <a name="a-namelgammafa--lgammaf-function"></a><a name="lgammaf"></a>Функция lgammaf  
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
  
##  <a name="a-nameloga--log-function"></a><a name="log"></a>Функция log  
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
  
##  <a name="a-namelog10a--log10-function"></a><a name="log10"></a>Функция LOG10  
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
  
##  <a name="a-namelog10fa--log10f-function"></a><a name="log10f"></a>Функция log10f  
 Вычисляет логарифм по основанию&10; аргумента  
  
```  
inline float log10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает десятичный логарифм аргумента  
  
##  <a name="a-namelog1pa--log1p-function"></a><a name="log1p"></a>Функция log1p  
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
  
##  <a name="a-namelog1pfa--log1pf-function"></a><a name="log1pf"></a>Функция log1pf  
 Вычисляет логарифм с основанием e 1, а также аргумент  
  
```  
inline float log1pf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает логарифм с основанием e 1, а также аргумент  
  
##  <a name="a-namelog2a--log2-function"></a><a name="log2"></a>Функция log2  
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
  
##  <a name="a-namelog2fa--log2f-function"></a><a name="log2f"></a>Функция log2f  
 Вычисляет логарифм по основанию&2; аргумента  
  
```  
inline float log2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает десятичный логарифм аргумента  
  
##  <a name="a-namelogba--logb-function"></a><a name="logb"></a>Функция logb  
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
  
##  <a name="a-namelogbfa--logbf-function"></a><a name="logbf"></a>Функция logbf  
 Извлекает экспоненты _X, как значение целого числа со знаком в формате с плавающей запятой  
  
```  
inline float logbf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение со знаком экспоненты _X  
  
##  <a name="a-namelogfa--logf-function"></a><a name="logf"></a>Функция logf  
 Вычисляет логарифм аргумента  
  
```  
inline float logf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает логарифм с основанием e аргумента  
  
##  <a name="a-namemodfa--modf-function"></a><a name="modf"></a>Функция modf  
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
  
##  <a name="a-namemodffa--modff-function"></a><a name="modff"></a>Функция modff  
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
  
##  <a name="a-namenana--nan-function"></a><a name="nan"></a>NaN-функция  
 Возвращает тихий NaN  
  
```  
inline double nan(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает несигнальным значением NaN, если в _X указано, доступные с содержимым  
  
##  <a name="a-namenanfa--nanf-function"></a><a name="nanf"></a>Функция nanf  
 Возвращает тихий NaN  
  
```  
inline float nanf(int _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает несигнальным значением NaN, если в _X указано, доступные с содержимым  
  
##  <a name="a-namenearbyinta--nearbyint-function"></a><a name="nearbyint"></a>Функция nearbyint  
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
  
##  <a name="a-namenearbyintfa--nearbyintf-function"></a><a name="nearbyintf"></a>Функция nearbyintf  
 Округляет аргумент целочисленного значения в формате с плавающей запятой, используя текущее направление округления.  
  
```  
inline float nearbyintf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает округленное целочисленное значение.  
  
##  <a name="a-namenextaftera--nextafter-function"></a><a name="nextafter"></a>Функция nextafter  
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
  
##  <a name="a-namenextafterfa--nextafterf-function"></a><a name="nextafterf"></a>Функция nextafterf  
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
  
##  <a name="a-namephia--phi-function"></a><a name="phi"></a>Функция PHI  
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
  
##  <a name="a-namephifa--phif-function"></a><a name="phif"></a>Функция phif  
 Возвращает интегральную функцию распределения аргумента  
  
```  
inline float phif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает интегральную функцию распределения аргумента  
  
##  <a name="a-namepowa--pow-function"></a><a name="pow"></a>Функция pow  
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
  
##  <a name="a-namepowfa--powf-function"></a><a name="powf"></a>Функция powf  
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
  
##  <a name="a-nameprobita--probit-function"></a><a name="probit"></a>Функция probit  
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
  
##  <a name="a-nameprobitfa--probitf-function"></a><a name="probitf"></a>Функция probitf  
 Возвращает обратный интегральную функцию распределения аргумента  
  
```  
inline float probitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратный интегральную функцию распределения аргумента  
  
##  <a name="a-namercbrta--rcbrt-function"></a><a name="rcbrt"></a>Функция rcbrt  
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
  
##  <a name="a-namercbrtfa--rcbrtf-function"></a><a name="rcbrtf"></a>Функция rcbrtf  
 Возвращает обратное кубический корень аргумента  
  
```  
inline float rcbrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратное кубический корень аргумента  
  
##  <a name="a-nameremaindera--remainder-function"></a><a name="remainder"></a>Функция Remainder  
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
  
##  <a name="a-nameremainderfa--remainderf-function"></a><a name="remainderf"></a>Функция remainderf  
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
  
##  <a name="a-nameremquoa--remquo-function"></a><a name="remquo"></a>Функция remquo  
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
  
##  <a name="a-nameremquofa--remquof-function"></a><a name="remquof"></a>Функция remquof  
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
  
##  <a name="a-namerounda--round-function"></a><a name="round"></a>Функция Round  
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
  
##  <a name="a-nameroundfa--roundf-function"></a><a name="roundf"></a>Функция roundf  
 Округляет _X до ближайшего целого числа  
  
```  
inline float roundf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает целое число, ближайшее из _X  
  
##  <a name="a-namersqrta--rsqrt-function"></a><a name="rsqrt"></a>Функция rsqrt  
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
  
##  <a name="a-namersqrtfa--rsqrtf-function"></a><a name="rsqrtf"></a>Функция rsqrtf  
 Возвращает обратное квадратного корня аргумент  
  
```  
inline float rsqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обратное квадратного корня аргумент  
  
##  <a name="a-namescalba--scalb-function"></a><a name="scalb"></a>Функция scalb  
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
  
##  <a name="a-namescalbfa--scalbf-function"></a><a name="scalbf"></a>Функция scalbf  
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
  
##  <a name="a-namescalbna--scalbn-function"></a><a name="scalbn"></a>Функция scalbn  
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
  
##  <a name="a-namescalbnfa--scalbnf-function"></a><a name="scalbnf"></a>Функция scalbnf  
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
  
##  <a name="a-namesignbita--signbit-function"></a><a name="signbit"></a>Функция signbit  
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
  
##  <a name="a-namesignbitfa--signbitf-function"></a><a name="signbitf"></a>Функция signbitf  
 Определяет, является ли знак _X отрицательное  
  
```  
inline int signbitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение только в том случае, если знак _X отрицательна  
  
##  <a name="a-namesina--sin-function"></a><a name="sin"></a>Функция sin  
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
  
##  <a name="a-namesinfa--sinf-function"></a><a name="sinf"></a>Функция sinf  
 Вычисляет синус аргумента  
  
```  
inline float sinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает синус аргумента  
  
##  <a name="a-namesincosa--sincos-function"></a><a name="sincos"></a>Функция sincos  
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
  
##  <a name="a-namesincosfa--sincosf-function"></a><a name="sincosf"></a>Функция sincosf  
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
  
##  <a name="a-namesinha--sinh-function"></a><a name="sinh"></a>Функция SINH  
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
  
##  <a name="a-namesinhfa--sinhf-function"></a><a name="sinhf"></a>Функция sinhf  
 Вычисляет гиперболический синус значение аргумента  
  
```  
inline float sinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает гиперболический синус значение аргумента  
  
##  <a name="a-namesinpia--sinpi-function"></a><a name="sinpi"></a>Функция sinpi  
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
  
##  <a name="a-namesinpifa--sinpif-function"></a><a name="sinpif"></a>Функция sinpif  
 Вычисляет синус числа пи * _X  
  
```  
inline float sinpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает синус числа пи * _X  
  
##  <a name="a-namesqrta--sqrt-function"></a><a name="sqrt"></a>Функция SQRT  
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
  
##  <a name="a-namesqrtfa--sqrtf-function"></a><a name="sqrtf"></a>Функция sqrtf  
 Вычисляет корень squre аргумента  
  
```  
inline float sqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает корень squre аргумента  
  
##  <a name="a-nametana--tan-function"></a><a name="tan"></a>Функция tan  
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
  
##  <a name="a-nametanfa--tanf-function"></a><a name="tanf"></a>Функция tanf  
 Вычисляет тангенс значение аргумента  
  
```  
inline float tanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тангенс значение аргумента  
  
##  <a name="a-nametanha--tanh-function"></a><a name="tanh"></a>Функция TANH  
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
  
##  <a name="a-nametanhfa--tanhf-function"></a><a name="tanhf"></a>Функция tanhf  
 Вычисляет гиперболический тангенс значение аргумента  
  
```  
inline float tanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает гиперболический тангенс значение аргумента  
  
##  <a name="a-nametanpia--tanpi-function"></a><a name="tanpi"></a>Функция tanpi  
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
  
##  <a name="a-nametanpifa--tanpif-function"></a><a name="tanpif"></a>Функция tanpif  
 Вычисляет тангенс числа пи * _X  
  
```  
inline float tanpif(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает тангенс числа пи * _X  
  
##  <a name="a-nametgammaa--tgamma-function"></a><a name="tgamma"></a>Функция tgamma  
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
  
##  <a name="a-nametgammafa--tgammaf-function"></a><a name="tgammaf"></a>Функция tgammaf  
 Вычисляет гамма-функции _X  
  
```  
inline float tgammaf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение гамма-функции из _X  
  
##  <a name="a-nametrunca--trunc-function"></a><a name="trunc"></a>Функция TRUNC  
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
  
##  <a name="a-nametruncfa--truncf-function"></a><a name="truncf"></a>Функция truncf  
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

