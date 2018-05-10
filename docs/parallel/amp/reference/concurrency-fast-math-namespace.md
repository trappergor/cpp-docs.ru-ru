---
title: Пространство имен Concurrency::fast_math | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- amp_math/Concurrency::fast_math
dev_langs:
- C++
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04a9cd3d604b18e42202bccb287cce7c7416b51f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="concurrencyfastmath-namespace"></a>Пространство имен Concurrency::fast_math
Функции в `fast_math` пространство имен имеет точность ниже, поддерживают только одинарной точности (`float`) и вызывать встроенные функции DirectX. Существуют две версии каждой функции, например `cos` и `cosf`. Обе версии, принимающие и возвращающие `float`, однако каждый вызов одной DirectX встроенная функция.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace fast_math;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Вычисляет арккосинус аргумента|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Вычисляет арккосинус аргумента|  
|[asin](concurrency-fast-math-namespace-functions.md#asin)|Вычисляет гиперболический арксинус аргумента|  
|[asinf](concurrency-fast-math-namespace-functions.md#asinf)|Вычисляет гиперболический арксинус аргумента|  
|[atan](concurrency-fast-math-namespace-functions.md#atan)|Вычисляет арктангенс аргумента.|  
|[atan2](concurrency-fast-math-namespace-functions.md#atan2)|Вычисляет арктангенс _Y/_X|  
|[atan2f](concurrency-fast-math-namespace-functions.md#atan2f)|Вычисляет арктангенс _Y/_X|  
|[atanf](concurrency-fast-math-namespace-functions.md#atanf)|Вычисляет арктангенс аргумента.|  
|[ceil](concurrency-fast-math-namespace-functions.md#ceil)|Вычисляет ceiling аргумента|  
|[ceilf](concurrency-fast-math-namespace-functions.md#ceilf)|Вычисляет ceiling аргумента|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Вычисляет косинус аргумента|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Вычисляет косинус аргумента|  
|[cosh](concurrency-fast-math-namespace-functions.md#cosh)|Вычисляет гиперболический косинус значение аргумента|  
|[coshf](concurrency-fast-math-namespace-functions.md#coshf)|Вычисляет гиперболический косинус значение аргумента|  
|[exp](concurrency-fast-math-namespace-functions.md#exp)|Вычисляет экспоненту аргумента base-e|  
|[exp2](concurrency-fast-math-namespace-functions.md#exp2)|Вычисляет экспоненту аргумента base-2|  
|[exp2f](concurrency-fast-math-namespace-functions.md#exp2f)|Вычисляет экспоненту аргумента base-2|  
|[expf](concurrency-fast-math-namespace-functions.md#expf)|Вычисляет экспоненту аргумента base-e|  
|[fabs](concurrency-fast-math-namespace-functions.md#fabs)|Возвращает абсолютное значение аргумента|  
|[fabsf](concurrency-fast-math-namespace-functions.md#fabsf)|Возвращает абсолютное значение аргумента|  
|[floor](concurrency-fast-math-namespace-functions.md#floor)|Вычисляет floor аргумента|  
|[floorf](concurrency-fast-math-namespace-functions.md#floorf)|Вычисляет floor аргумента|  
|[fmax](concurrency-fast-math-namespace-functions.md#fmax)|Определите максимальное числовое значение аргументов|  
|[fmaxf](concurrency-fast-math-namespace-functions.md#fmaxf)|Определите максимальное числовое значение аргументов|  
|[fmin](concurrency-fast-math-namespace-functions.md#fmin)|Определите минимальное числовое значение аргументов|  
|[fminf](concurrency-fast-math-namespace-functions.md#fminf)|Определите минимальное числовое значение аргументов|  
|[fmod](concurrency-fast-math-namespace-functions.md#fmod)|Вычисляет остаток с плавающей запятой от _X/_Y|  
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|Вычисляет остаток с плавающей запятой от _X/_Y|  
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|Возвращает мантисса и степень из _X|  
|[frexpf](concurrency-fast-math-namespace-functions.md#frexpf)|Возвращает мантисса и степень из _X|  
|[isfinite](concurrency-fast-math-namespace-functions.md#isfinite)|Определяет, имеет ли аргумент конечное значение|  
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|Определяет, является ли аргумент бесконечности|  
|[isnan](concurrency-fast-math-namespace-functions.md#isnan)|Определяет, является ли аргумент NaN|  
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|Вычисляет вещественное число от мантисса и степень|  
|[ldexpf](concurrency-fast-math-namespace-functions.md#ldexpf)|Вычисляет вещественное число от мантисса и степень|  
|[log](concurrency-fast-math-namespace-functions.md#log)|Вычисляет логарифм с основанием e аргумента|  
|[log10](concurrency-fast-math-namespace-functions.md#log10)|Вычисляет логарифм по основанию 10 аргумента|  
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|Вычисляет логарифм по основанию 10 аргумента|  
|[log2](concurrency-fast-math-namespace-functions.md#log2)|Вычисляет логарифм по основанию 2 аргумента|  
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|Вычисляет логарифм по основанию 2 аргумента|  
|[logf](concurrency-fast-math-namespace-functions.md#logf)|Вычисляет логарифм с основанием e аргумента|  
|[modf](concurrency-fast-math-namespace-functions.md#modf)|Разбивает _X в долях и частей целое число со знаком.|  
|[modff](concurrency-fast-math-namespace-functions.md#modff)|Разбивает _X в долях и частей целое число со знаком.|  
|[pow](concurrency-fast-math-namespace-functions.md#pow)|Вычисляет _X, возведенное в степень _Y|  
|[powf](concurrency-fast-math-namespace-functions.md#powf)|Вычисляет _X, возведенное в степень _Y|  
|[round](concurrency-fast-math-namespace-functions.md#round)|Округляет _X до ближайшего целого|  
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|Округляет _X до ближайшего целого|  
|[rsqrt](concurrency-fast-math-namespace-functions.md#rsqrt)|Возвращает обратное квадратного корня аргумент|  
|[rsqrtf](concurrency-fast-math-namespace-functions.md#rsqrtf)|Возвращает обратное квадратного корня аргумент|  
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|Возвращает знак значения аргумента|  
|[signbitf](concurrency-fast-math-namespace-functions.md#signbitf)|Возвращает знак значения аргумента|  
|[sin](concurrency-fast-math-namespace-functions.md#sin)|Вычисляет синус аргумента|  
|[sincos](concurrency-fast-math-namespace-functions.md#sincos)|Вычисляет синус и косинус значение _X|  
|[sincosf](concurrency-fast-math-namespace-functions.md#sincosf)|Вычисляет синус и косинус значение _X|  
|[sinf](concurrency-fast-math-namespace-functions.md#sinf)|Вычисляет синус аргумента|  
|[sinh](concurrency-fast-math-namespace-functions.md#sinh)|Вычисляет гиперболический синус значение аргумента|  
|[sinhf](concurrency-fast-math-namespace-functions.md#sinhf)|Вычисляет гиперболический синус значение аргумента|  
|[sqrt](concurrency-fast-math-namespace-functions.md#sqrt)|Вычисляет квадратный корень аргумента|  
|[sqrtf](concurrency-fast-math-namespace-functions.md#sqrtf)|Вычисляет квадратный корень аргумента|  
|[tan](concurrency-fast-math-namespace-functions.md#tan)|Вычисляет тангенс значение аргумента|  
|[tanf](concurrency-fast-math-namespace-functions.md#tanf)|Вычисляет тангенс значение аргумента|  
|[tanh](concurrency-fast-math-namespace-functions.md#tanh)|Вычисляет гиперболический тангенс значение аргумента|  
|[tanhf](concurrency-fast-math-namespace-functions.md#tanhf)|Вычисляет гиперболический тангенс значение аргумента|  
|[trunc](concurrency-fast-math-namespace-functions.md#trunc)|Усекает целочисленный аргумент|  
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|Усекает целочисленный аргумент|  

## <a name="requirements"></a>Требования  
 **Заголовок:** amp_math.h  
  
 **Пространство имен:** Concurrency::fast_math  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
