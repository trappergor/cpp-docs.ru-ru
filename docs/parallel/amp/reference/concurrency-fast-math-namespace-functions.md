---
title: "Функции пространство имен Concurrency::fast_math | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4a01f48a7d087281ab1e9222d1077e92ab8b0d6c
ms.openlocfilehash: 0545a57c492f5c1872c71c04c99b54f86b644102
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyfastmath-namespace-functions"></a>Функции пространство имен Concurrency::fast_math
||||  
|-|-|-|  
|[Функция ACOS](#acos)|[Функция acosf](#acosf)|[Функция ASIN](#asin)|  
|[Функция asinf](#asinf)|[Функция ATAN](#atan)|[Функция ATAN2](#atan2)|  
|[Функция atan2f](#atan2f)|[Функция atanf](#atanf)|[Функция ceil](#ceil)|  
|[Функция ceilf](#ceilf)|[cos функции](#cos)|[Функция cosf](#cosf)|  
|[Функция COSH](#cosh)|[Функция coshf](#coshf)|[Функция EXP](#exp)|  
|[Функция exp2](#exp2)|[Функция exp2f](#exp2f)|[Функция expf](#expf)|  
|[Функция fabs](#fabs)|[Функция fabsf](#fabsf)|[Функция FLOOR](#floor)|  
|[Функция floorf](#floorf)|[Функция fmax](#fmax)|[Функция fmaxf](#fmaxf)|  
|[Функция fmin](#fmin)|[Функция fminf](#fminf)|[Функция fmod](#fmod)|  
|[Функция fmodf](#fmodf)|[Функция frexp](#frexp)|[Функция frexpf](#frexpf)|  
|[Функция isFinite](#isfinite)|[Функция isinf](#isinf)|[Функция isNaN](#isnan)|  
|[Функция ldexp](#ldexp)|[Функция ldexpf](#ldexpf)|[Функция log](#log)|  
|[Функция LOG10](#log10)|[Функция log10f](#log10f)|[Функция log2](#log2)|  
|[Функция log2f](#log2f)|[Функция logf](#logf)|[Функция modf](#modf)|  
|[Функция modff](#modff)|[Функция pow](#pow)|[Функция powf](#powf)|  
|[Функция Round](#round)|[Функция roundf](#roundf)|[Функция rsqrt](#rsqrt)|  
|[Функция rsqrtf](#rsqrtf)|[Функция signbit](#signbit)|[Функция signbitf](#signbitf)|  
|[Функция sin](#sin)|[Функция sincos](#sincos)|[Функция sincosf](#sincosf)|  
|[Функция sinf](#sinf)|[Функция SINH](#sinh)|[Функция sinhf](#sinhf)|  
|[Функция SQRT](#sqrt)|[Функция sqrtf](#sqrtf)|[Функция tan](#tan)|  
|[Функция tanf](#tanf)|[Функция TANH](#tanh)|[Функция tanhf](#tanhf)|  
|[Функция TRUNC](#trunc)|[Функция truncf](#truncf)|  
  
##  <a name="a-nameacosa--acos-function"></a><a name="acos"></a>Функция ACOS  
 Вычисляет арккосинус аргумента  
  
```  
inline float acos(float _X) restrict(amp);
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
  
##  <a name="a-nameasina--asin-function"></a><a name="asin"></a>Функция ASIN  
 Вычисляет гиперболический арксинус аргумента  
  
```  
inline float asin(float _X) restrict(amp);
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
  
##  <a name="a-nameatana--atan-function"></a><a name="atan"></a>Функция ATAN  
 Вычисляет арктангенс аргумента.  
  
```  
inline float atan(float _X) restrict(amp);
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
  
##  <a name="a-nameceila--ceil-function"></a><a name="ceil"></a>Функция ceil  
 Вычисляет ceiling аргумента  
  
```  
inline float ceil(float _X) restrict(amp);
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
  
##  <a name="a-namecosa--cos-function"></a><a name="cos"></a>cos функции   
 Вычисляет косинус аргумента  
  
```  
inline float cos(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает гиперболический косинус значение аргумента  
  
##  <a name="a-nameexpa--exp-function"></a><a name="exp"></a>Функция EXP  
 Вычисляет экспоненту аргумента base-e  
  
```  
inline float exp(float _X) restrict(amp);
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
  
##  <a name="a-namefabsa--fabs-function"></a><a name="fabs"></a>Функция fabs  
 Возвращает абсолютное значение аргумента  
  
```  
inline float fabs(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
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
  
##  <a name="a-namefloora--floor-function"></a><a name="floor"></a>Функция FLOOR  
 Вычисляет floor аргумента  
  
```  
inline float floor(float _X) restrict(amp);
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
  
##  <a name="a-namefmaxa--fmax-function"></a><a name="fmax"></a>Функция fmax  
 Определите максимальное числовое значение аргументов  
  
```  
inline float max(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
 `_Y`  
 Целое значение  
  
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
inline float min(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Целое значение  
  
 `_Y`  
 Целое значение  
  
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
  
##  <a name="a-namefmoda--fmod-function"></a><a name="fmod"></a>Функция fmod  
 Вычисляет остаток с плавающей запятой от _X или _Y  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает остаток с плавающей запятой _X или _Y  
  
##  <a name="a-namefmodfa--fmodf-function"></a><a name="fmodf"></a>Функция fmodf  
 Вычисляет остаток с плавающей запятой от _X или _Y.  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Y`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает остаток с плавающей запятой _X или _Y  
  
##  <a name="a-namefrexpa--frexp-function"></a><a name="frexp"></a>Функция frexp  
 Возвращает мантиссы и экспоненты _X  
  
```  
inline float frexp(
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
  
##  <a name="a-nameisfinitea--isfinite-function"></a><a name="isfinite"></a>Функция isFinite  
 Определяет, имеет ли аргумент конечное значение  
  
```  
inline int isfinite(float _X) restrict(amp);
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
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение только в том случае, если аргумент имеет значение NaN  
  
##  <a name="a-nameldexpa--ldexp-function"></a><a name="ldexp"></a>Функция ldexp  
 Вычисляет действительное число мантисса и степень  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой, mentissa  
  
 `_Exp`  
 Целый показатель степени  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X * 2 ^ _Exp  
  
##  <a name="a-nameldexpfa--ldexpf-function"></a><a name="ldexpf"></a>Функция ldexpf  
 Вычисляет действительное число мантисса и степень  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой, mentissa  
  
 `_Exp`  
 Целый показатель степени  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает _X * 2 ^ _Exp  
  
##  <a name="a-nameloga--log-function"></a><a name="log"></a>Функция log  
 Вычисляет логарифм аргумента  
  
```  
inline float log(float _X) restrict(amp);
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
  
##  <a name="a-namelog2a--log2-function"></a><a name="log2"></a>Функция log2  
 Вычисляет логарифм по основанию&2; аргумента  
  
```  
inline float log2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает логарифм по основанию&2; аргумента  
  
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
 Разделяет _X в долях и целое число частей.  
  
```  
inline float modf(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Ip`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает подписанный дробной части числа _X  
  
##  <a name="a-namemodffa--modff-function"></a><a name="modff"></a>Функция modff  
 Разделяет _X в долях и целое число частей.  
  
```  
inline float modff(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой  
  
 `_Ip`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает подписанный дробной части числа _X  
  
##  <a name="a-namepowa--pow-function"></a><a name="pow"></a>Функция pow  
 Вычисляет _X, возведенное в степень _Y  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_X`  
 Значение с плавающей запятой, базовый  
  
 `_Y`  
 Значение с плавающей запятой, показатель степени  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, возведенное в степень _Y _X  
  
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
  
##  <a name="a-namerounda--round-function"></a><a name="round"></a>Функция Round  
 Округляет _X до ближайшего целого числа  
  
```  
inline float round(float _X) restrict(amp);
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
  
##  <a name="a-namesignbita--signbit-function"></a><a name="signbit"></a>Функция signbit  
 Определяет, является ли знак _X отрицательное  
  
```  
inline int signbit(float _X) restrict(amp);
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
    float* _S,  
    float* _C) restrict(amp);
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
    float* _S,  
    float* _C) restrict(amp);
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
  
##  <a name="a-namesqrta--sqrt-function"></a><a name="sqrt"></a>Функция SQRT  
 Вычисляет корень squre аргумента  
  
```  
inline float sqrt(float _X) restrict(amp);
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
  
##  <a name="a-nametrunca--trunc-function"></a><a name="trunc"></a>Функция TRUNC  
 Усекает для целочисленный аргумент  
  
```  
inline float trunc(float _X) restrict(amp);
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
 [Пространство имен Concurrency::fast_math](concurrency-fast-math-namespace.md)

