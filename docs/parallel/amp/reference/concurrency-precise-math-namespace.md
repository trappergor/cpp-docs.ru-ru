---
title: "Пространство имен Concurrency::precise_math | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::precise_math
dev_langs:
- C++
ms.assetid: ba653308-dc28-4384-b2fd-6cd718a72f91
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b64bd3e3702701ae2685d6688d88988dd91dc5d0
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyprecisemath-namespace"></a>Пространство имен Concurrency::precise_math
Функции в `precise_math` пространства имен являются совместимыми C99. Оба одиночной точности и включены двойной точности версии каждой функции. Например `acos` версия двойной точности и `acosf` версия одиночной точности. Эти функции, включая функции одиночной точности, требуется расширенная поддержка двойной точности на сочетания клавиш. Можно использовать [данных accelerator::supports_double_precision](accelerator-class.md#supports_double_precision) для определения, если эти функции можно запустить на определенных сочетаний клавиш. 

  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
namespace precise_math;  
```  
  
#### <a name="parameters"></a>Параметры  
  
## <a name="members"></a>Члены  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функция ACOS](concurrency-precise-math-namespace-functions.md#acos)|Перегружен. Вычисляет арккосинус аргумента|  
|[Функция acosf](concurrency-precise-math-namespace-functions.md#acosf)|Вычисляет арккосинус аргумента|  
|[Функция ACOSH](concurrency-precise-math-namespace-functions.md#acosh)|Перегружен. Вычисляет гиперболический арккосинус аргумента|  
|[Функция acoshf](concurrency-precise-math-namespace-functions.md#acoshf)|Вычисляет гиперболический арккосинус аргумента|  
|[Функция ASIN](concurrency-precise-math-namespace-functions.md#asin)|Перегружен. Вычисляет гиперболический арксинус аргумента|  
|[Функция asinf](concurrency-precise-math-namespace-functions.md#asinf)|Вычисляет гиперболический арксинус аргумента|  
|[Функция ASINH](concurrency-precise-math-namespace-functions.md#asinh)|Перегружен. Вычисляет гиперболический арксинус аргумента|  
|[Функция asinhf](concurrency-precise-math-namespace-functions.md#asinhf)|Вычисляет гиперболический арксинус аргумента|  
|[Функция ATAN](concurrency-precise-math-namespace-functions.md#atan)|Перегружен. Вычисляет арктангенс аргумента.|  
|[Функция ATAN2](concurrency-precise-math-namespace-functions.md#atan2)|Перегружен. Вычисляет арктангенс _Y или _X|  
|[Функция atan2f](concurrency-precise-math-namespace-functions.md#atan2f)|Вычисляет арктангенс _Y или _X|  
|[Функция atanf](concurrency-precise-math-namespace-functions.md#atanf)|Вычисляет арктангенс аргумента.|  
|[Функция ATANH](concurrency-precise-math-namespace-functions.md#atanh)|Перегружен. Вычисляет гиперболический арктангенс аргумента|  
|[Функция atanhf](concurrency-precise-math-namespace-functions.md#atanhf)|Вычисляет гиперболический арктангенс аргумента|  
|[Функция cbrt](concurrency-precise-math-namespace-functions.md#cbrt)|Перегружен. Вычисляет кубический корень реальных аргумента|  
|[Функция cbrtf](concurrency-precise-math-namespace-functions.md#cbrtf)|Вычисляет кубический корень реальных аргумента|  
|[Функция ceil](concurrency-precise-math-namespace-functions.md#ceil)|Перегружен. Вычисляет ceiling аргумента|  
|[Функция ceilf](concurrency-precise-math-namespace-functions.md#ceilf)|Вычисляет ceiling аргумента|  
|[Функция copysign](concurrency-precise-math-namespace-functions.md#copysign)|Перегружен. Возвращает значение, указывающее величину _X и знак _Y|  
|[Функция copysignf](concurrency-precise-math-namespace-functions.md#copysignf)|Возвращает значение, указывающее величину _X и знак _Y|  
|[cos функции](concurrency-precise-math-namespace-functions.md#cos)|Перегружен. Вычисляет косинус аргумента|  
|[Функция cosf](concurrency-precise-math-namespace-functions.md#cosf)|Вычисляет косинус аргумента|  
|[Функция COSH](concurrency-precise-math-namespace-functions.md#cosh)|Перегружен. Вычисляет гиперболический косинус значение аргумента|  
|[Функция coshf](concurrency-precise-math-namespace-functions.md#coshf)|Вычисляет гиперболический косинус значение аргумента|  
|[Функция cospi](concurrency-precise-math-namespace-functions.md#cospi)|Перегружен. Вычисляет косинус числа пи * _X|  
|[Функция cospif](concurrency-precise-math-namespace-functions.md#cospif)|Вычисляет косинус числа пи * _X|  
|[Функция erf](concurrency-precise-math-namespace-functions.md#erf)|Перегружен. Вычисляет функцию ошибок _X|  
|[Функция erfc](concurrency-precise-math-namespace-functions.md#erfc)|Перегружен. Вычисляет дополнительную функцию ошибок _X|  
|[Функция erfcf](concurrency-precise-math-namespace-functions.md#erfcf)|Вычисляет дополнительную функцию ошибок _X|  
|[Функция erfcinv](concurrency-precise-math-namespace-functions.md#erfcinv)|Перегружен. Вычисляет обратный дополнительную функцию ошибок _X|  
|[Функция erfcinvf](concurrency-precise-math-namespace-functions.md#erfcinvf)|Вычисляет обратный дополнительную функцию ошибок _X|  
|[Функция erff](concurrency-precise-math-namespace-functions.md#erff)|Вычисляет функцию ошибок _X|  
|[Функция erfinv](concurrency-precise-math-namespace-functions.md#erfinv)|Перегружен. Вычисляет обратный ошибок _X|  
|[Функция erfinvf](concurrency-precise-math-namespace-functions.md#erfinvf)|Вычисляет обратный ошибок _X|  
|[Функция EXP](concurrency-precise-math-namespace-functions.md#exp)|Перегружен. Вычисляет экспоненту аргумента base-e|  
|[Функция exp10](concurrency-precise-math-namespace-functions.md#exp10)|Перегружен. Вычисляет экспоненту аргумента base-10|  
|[Функция exp10f](concurrency-precise-math-namespace-functions.md#exp10f)|Вычисляет экспоненту аргумента base-10|  
|[Функция exp2](concurrency-precise-math-namespace-functions.md#exp2)|Перегружен. Вычисляет экспоненту аргумента base-2|  
|[Функция exp2f](concurrency-precise-math-namespace-functions.md#exp2f)|Вычисляет экспоненту аргумента base-2|  
|[Функция expf](concurrency-precise-math-namespace-functions.md#expf)|Вычисляет экспоненту аргумента base-e|  
|[Функция expm1](concurrency-precise-math-namespace-functions.md#expm1)|Перегружен. Вычисляет экспоненту аргумента с основанием e, за вычетом 1|  
|[Функция expm1f](concurrency-precise-math-namespace-functions.md#expm1f)|Вычисляет экспоненту аргумента с основанием e, за вычетом 1|  
|[Функция fabs](concurrency-precise-math-namespace-functions.md#fabs)|Перегружен. Возвращает абсолютное значение аргумента|  
|[Функция fabsf](concurrency-precise-math-namespace-functions.md#fabsf)|Возвращает абсолютное значение аргумента|  
|[Функция fdim](concurrency-precise-math-namespace-functions.md#fdim)|Перегружен. Определяет положительной разнице между аргументами|  
|[Функция fdimf](concurrency-precise-math-namespace-functions.md#fdimf)|Определяет положительной разнице между аргументами|  
|[Функция FLOOR](concurrency-precise-math-namespace-functions.md#floor)|Перегружен. Вычисляет floor аргумента|  
|[Функция floorf](concurrency-precise-math-namespace-functions.md#floorf)|Вычисляет floor аргумента|  
|[Функция FMA](concurrency-precise-math-namespace-functions.md#fma)|Перегружен. Вычисления (_X * _Y) + _Z, с округлением в рамках одной операции троичный|  
|[Функция fmaf](concurrency-precise-math-namespace-functions.md#fmaf)|Вычисления (_X * _Y) + _Z, с округлением в рамках одной операции троичный|  
|[Функция fmax](concurrency-precise-math-namespace-functions.md#fmax)|Перегружен. Определите максимальное числовое значение аргументов|  
|[Функция fmaxf](concurrency-precise-math-namespace-functions.md#fmaxf)|Определите максимальное числовое значение аргументов|  
|[Функция fmin](concurrency-precise-math-namespace-functions.md#fmin)|Перегружен. Определите минимальное числовое значение аргументов|  
|[Функция fminf](concurrency-precise-math-namespace-functions.md#fminf)|Определите минимальное числовое значение аргументов|  
|[Функция fmod (C++ AMP)](concurrency-precise-math-namespace-functions.md#fmod)|Перегружен. Вычисляет остаток с плавающей запятой от _X или _Y|  
|[Функция fmodf](concurrency-precise-math-namespace-functions.md#fmodf)|Вычисляет остаток с плавающей запятой от _X или _Y|  
|[Функция fpclassify](concurrency-precise-math-namespace-functions.md#fpclassify)|Перегружен. Классифицирует значение аргумента как нулевое значение NaN, бесконечное, обычная, subnormal,|  
|[Функция frexp](concurrency-precise-math-namespace-functions.md#frexp)|Перегружен. Возвращает мантиссы и экспоненты _X|  
|[Функция frexpf](concurrency-precise-math-namespace-functions.md#frexpf)|Возвращает мантиссы и экспоненты _X|  
|[Функция hypot](concurrency-precise-math-namespace-functions.md#hypot)|Перегружен. Вычисляет квадратный корень из суммы квадратов _X и _Y|  
|[Функция hypotf](concurrency-precise-math-namespace-functions.md#hypotf)|Вычисляет квадратный корень из суммы квадратов _X и _Y|  
|[Функция ilogb](concurrency-precise-math-namespace-functions.md#ilogb)|Перегружен. Извлеките экспоненты _X как значение типа int со знаком|  
|[Функция ilogbf](concurrency-precise-math-namespace-functions.md#ilogbf)|Извлеките экспоненты _X как значение типа int со знаком|  
|[Функция isFinite](concurrency-precise-math-namespace-functions.md#isfinite)|Перегружен. Определяет, имеет ли аргумент конечное значение|  
|[Функция isinf](concurrency-precise-math-namespace-functions.md#isinf)|Перегружен. Определяет, является ли аргумент бесконечности|  
|[Функция isNaN](concurrency-precise-math-namespace-functions.md#isnan)|Перегружен. Определяет, является ли аргумент значение NaN|  
|[Функция isnormal](concurrency-precise-math-namespace-functions.md#isnormal)|Перегружен. Определяет, является ли аргумент норм.|  
|[Функция ldexp](concurrency-precise-math-namespace-functions.md#ldexp)|Перегружен. Вычисляет действительное число мантисса и степень|  
|[Функция ldexpf](concurrency-precise-math-namespace-functions.md#ldexpf)|Вычисляет действительное число мантисса и степень|  
|[Функция lgamma](concurrency-precise-math-namespace-functions.md#lgamma)|Перегружен. Вычисляет натуральный логарифм гамма аргумента абсолютное значение|  
|[Функция lgammaf](concurrency-precise-math-namespace-functions.md#lgammaf)|Вычисляет натуральный логарифм гамма аргумента абсолютное значение|  
|[Функция log](concurrency-precise-math-namespace-functions.md#log)|Перегружен. Вычисляет логарифм аргумента|  
|[Функция LOG10](concurrency-precise-math-namespace-functions.md#log10)|Перегружен. Вычисляет логарифм по основанию&10; аргумента|  
|[Функция log10f](concurrency-precise-math-namespace-functions.md#log10f)|Вычисляет логарифм по основанию&10; аргумента|  
|[Функция log1p](concurrency-precise-math-namespace-functions.md#log1p)|Перегружен. Вычисляет логарифм с основанием e 1, а также аргумент|  
|[Функция log1pf](concurrency-precise-math-namespace-functions.md#log1pf)|Вычисляет логарифм с основанием e 1, а также аргумент|  
|[Функция log2](concurrency-precise-math-namespace-functions.md#log2)|Перегружен. Вычисляет логарифм по основанию&2; аргумента|  
|[Функция log2f](concurrency-precise-math-namespace-functions.md#log2f)|Вычисляет логарифм по основанию&2; аргумента|  
|[Функция logb](concurrency-precise-math-namespace-functions.md#logb)|Перегружен. Извлекает экспоненты _X, как значение целого числа со знаком в формате с плавающей запятой|  
|[Функция logbf](concurrency-precise-math-namespace-functions.md#logbf)|Извлекает экспоненты _X, как значение целого числа со знаком в формате с плавающей запятой|  
|[Функция logf](concurrency-precise-math-namespace-functions.md#logf)|Вычисляет логарифм аргумента|  
|[Функция modf](concurrency-precise-math-namespace-functions.md#modf)|Перегружен. Разделяет _X в долях и целое число частей.|  
|[Функция modff](concurrency-precise-math-namespace-functions.md#modff)|Разделяет _X в долях и целое число частей.|  
|[NaN-функция](concurrency-precise-math-namespace-functions.md#nan)|Возвращает тихий NaN|  
|[Функция nanf](concurrency-precise-math-namespace-functions.md#nanf)|Возвращает тихий NaN|  
|[Функция nearbyint](concurrency-precise-math-namespace-functions.md#nearbyint)|Перегружен. Округляет аргумент целочисленного значения в формате с плавающей запятой, используя текущее направление округления.|  
|[Функция nearbyintf](concurrency-precise-math-namespace-functions.md#nearbyintf)|Округляет аргумент целочисленного значения в формате с плавающей запятой, используя текущее направление округления.|  
|[Функция nextafter](concurrency-precise-math-namespace-functions.md#nextafter)|Перегружен. Определить Далее представимым значением типа функции, после _X в направлении _Y|  
|[Функция nextafterf](concurrency-precise-math-namespace-functions.md#nextafterf)|Определить Далее представимым значением типа функции, после _X в направлении _Y|  
|[Функция PHI](concurrency-precise-math-namespace-functions.md#phi)|Перегружен. Возвращает интегральную функцию распределения аргумента|  
|[Функция phif](concurrency-precise-math-namespace-functions.md#phif)|Возвращает интегральную функцию распределения аргумента|  
|[Функция pow](concurrency-precise-math-namespace-functions.md#pow)|Перегружен. Вычисляет _X, возведенное в степень _Y|  
|[Функция powf](concurrency-precise-math-namespace-functions.md#powf)|Вычисляет _X, возведенное в степень _Y|  
|[Функция probit](concurrency-precise-math-namespace-functions.md#probit)|Перегружен. Возвращает обратный интегральную функцию распределения аргумента|  
|[Функция probitf](concurrency-precise-math-namespace-functions.md#probitf)|Возвращает обратный интегральную функцию распределения аргумента|  
|[Функция rcbrt](concurrency-precise-math-namespace-functions.md#rcbrt)|Перегружен. Возвращает обратное кубический корень аргумента|  
|[Функция rcbrtf](concurrency-precise-math-namespace-functions.md#rcbrtf)|Возвращает обратное кубический корень аргумента|  
|[Функция Remainder](concurrency-precise-math-namespace-functions.md#remainder)|Перегружен. Вычисляет остаток: _X REM _Y|  
|[Функция remainderf](concurrency-precise-math-namespace-functions.md#remainderf)|Вычисляет остаток: _X REM _Y|  
|[Функция remquo](concurrency-precise-math-namespace-functions.md#remquo)|Перегружен. Вычисляет остаток же как _X REM _Y. Также вычисляет младших битов 23 _X целочисленное частное и _Y и дает тот же знак _X или _Y это значение. Она сохраняет это значение со знаком в целое число со знаком, который указывает _Quo.|  
|[Функция remquof](concurrency-precise-math-namespace-functions.md#remquof)|Вычисляет остаток же как _X REM _Y. Также вычисляет младших битов 23 _X целочисленное частное и _Y и дает тот же знак _X или _Y это значение. Она сохраняет это значение со знаком в целое число со знаком, который указывает _Quo.|  
|[Функция Round](concurrency-precise-math-namespace-functions.md#round)|Перегружен. Округляет _X до ближайшего целого числа|  
|[Функция roundf](concurrency-precise-math-namespace-functions.md#roundf)|Округляет _X до ближайшего целого числа|  
|[Функция rsqrt](concurrency-precise-math-namespace-functions.md#rsqrt)|Перегружен. Возвращает обратное квадратного корня аргумент|  
|[Функция rsqrtf](concurrency-precise-math-namespace-functions.md#rsqrtf)|Возвращает обратное квадратного корня аргумент|  
|[Функция scalb](concurrency-precise-math-namespace-functions.md#scalb)|Перегружен. Умножает _X константой FLT_RADIX для _Y питания|  
|[Функция scalbf](concurrency-precise-math-namespace-functions.md#scalbf)|Умножает _X константой FLT_RADIX для _Y питания|  
|[Функция scalbn](concurrency-precise-math-namespace-functions.md#scalbn)|Перегружен. Умножает _X константой FLT_RADIX для _Y питания|  
|[Функция scalbnf](concurrency-precise-math-namespace-functions.md#scalbnf)|Умножает _X константой FLT_RADIX для _Y питания|  
|[Функция signbit](concurrency-precise-math-namespace-functions.md#signbit)|Перегружен. Определяет, является ли знак _X отрицательное|  
|[Функция signbitf](concurrency-precise-math-namespace-functions.md#signbitf)|Определяет, является ли знак _X отрицательное|  
|[Функция sin](concurrency-precise-math-namespace-functions.md#sin)|Перегружен. Вычисляет синус аргумента|  
|[Функция sincos](concurrency-precise-math-namespace-functions.md#sincos)|Перегружен. Вычисляет синус и косинус значение _X|  
|[Функция sincosf](concurrency-precise-math-namespace-functions.md#sincosf)|Вычисляет синус и косинус значение _X|  
|[Функция sinf](concurrency-precise-math-namespace-functions.md#sinf)|Вычисляет синус аргумента|  
|[Функция SINH](concurrency-precise-math-namespace-functions.md#sinh)|Перегружен. Вычисляет гиперболический синус значение аргумента|  
|[Функция sinhf](concurrency-precise-math-namespace-functions.md#sinhf)|Вычисляет гиперболический синус значение аргумента|  
|[Функция sinpi](concurrency-precise-math-namespace-functions.md#sinpi)|Перегружен. Вычисляет синус числа пи * _X|  
|[Функция sinpif](concurrency-precise-math-namespace-functions.md#sinpif)|Вычисляет синус числа пи * _X|  
|[Функция SQRT](concurrency-precise-math-namespace-functions.md#sqrt)|Перегружен. Вычисляет корень squre аргумента|  
|[Функция sqrtf](concurrency-precise-math-namespace-functions.md#sqrtf)|Вычисляет корень squre аргумента|  
|[Функция tan](concurrency-precise-math-namespace-functions.md#tan)|Перегружен. Вычисляет тангенс значение аргумента|  
|[Функция tanf](concurrency-precise-math-namespace-functions.md#tanf)|Вычисляет тангенс значение аргумента|  
|[Функция TANH](concurrency-precise-math-namespace-functions.md#tanh)|Перегружен. Вычисляет гиперболический тангенс значение аргумента|  
|[Функция tanhf](concurrency-precise-math-namespace-functions.md#tanhf)|Вычисляет гиперболический тангенс значение аргумента|  
|[Функция tanpi](concurrency-precise-math-namespace-functions.md#tanpi)|Перегружен. Вычисляет тангенс числа пи * _X|  
|[Функция tanpif](concurrency-precise-math-namespace-functions.md#tanpif)|Вычисляет тангенс числа пи * _X|  
|[Функция tgamma](concurrency-precise-math-namespace-functions.md#tgamma)|Перегружен. Вычисляет гамма-функции _X|  
|[Функция tgammaf](concurrency-precise-math-namespace-functions.md#tgammaf)|Вычисляет гамма-функции _X|  
|[Функция TRUNC](concurrency-precise-math-namespace-functions.md#trunc)|Перегружен. Усекает для целочисленный аргумент|  
|[Функция truncf](concurrency-precise-math-namespace-functions.md#truncf)|Усекает для целочисленный аргумент|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_math.h  
  
 **Пространство имен** : Concurrency  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

