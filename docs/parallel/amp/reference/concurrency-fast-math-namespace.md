---
title: Пространство имен Concurrency::fast_math | Документация Майкрософт
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
ms.openlocfilehash: dd39e2057225aa09fd0bf0907e90abbf79b16172
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410290"
---
# <a name="concurrencyfastmath-namespace"></a>Пространство имен Concurrency::fast_math

Функции в `fast_math` пространства имен имеют более низкую точность, поддерживают только одиночную точность (`float`) и вызывать встроенные функции DirectX. Существуют две версии каждой функции, например `cos` и `cosf`. Обе версии принимают и возвращают `float`, но каждая вызывает функцию же DirectX внутренние.

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
|[ceil](concurrency-fast-math-namespace-functions.md#ceil)|Вычисляет максимальное значение аргумента|
|[ceilf](concurrency-fast-math-namespace-functions.md#ceilf)|Вычисляет максимальное значение аргумента|
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Вычисляет косинус аргумента|
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Вычисляет косинус аргумента|
|[cosh](concurrency-fast-math-namespace-functions.md#cosh)|Вычисляет значение гиперболического косинуса аргумента|
|[coshf](concurrency-fast-math-namespace-functions.md#coshf)|Вычисляет значение гиперболического косинуса аргумента|
|[exp](concurrency-fast-math-namespace-functions.md#exp)|Вычисляет экспоненту аргумента base-e|
|[exp2](concurrency-fast-math-namespace-functions.md#exp2)|Вычисляет экспоненту аргумента base-2|
|[exp2f](concurrency-fast-math-namespace-functions.md#exp2f)|Вычисляет экспоненту аргумента base-2|
|[expf](concurrency-fast-math-namespace-functions.md#expf)|Вычисляет экспоненту аргумента base-e|
|[fabs](concurrency-fast-math-namespace-functions.md#fabs)|Возвращает абсолютное значение аргумента|
|[fabsf](concurrency-fast-math-namespace-functions.md#fabsf)|Возвращает абсолютное значение аргумента|
|[floor](concurrency-fast-math-namespace-functions.md#floor)|Вычисляет минимальное значение аргумента|
|[floorf](concurrency-fast-math-namespace-functions.md#floorf)|Вычисляет минимальное значение аргумента|
|[fmax](concurrency-fast-math-namespace-functions.md#fmax)|Определение максимального числового значения аргументов|
|[fmaxf](concurrency-fast-math-namespace-functions.md#fmaxf)|Определение максимального числового значения аргументов|
|[fmin](concurrency-fast-math-namespace-functions.md#fmin)|Определение минимального числового значения аргументов|
|[fminf](concurrency-fast-math-namespace-functions.md#fminf)|Определение минимального числового значения аргументов|
|[fmod](concurrency-fast-math-namespace-functions.md#fmod)|Вычисляет остаток с плавающей запятой от _X/_Y|
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|Вычисляет остаток с плавающей запятой от _X/_Y|
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|Получает мантиссу и экспоненту _X|
|[frexpf](concurrency-fast-math-namespace-functions.md#frexpf)|Получает мантиссу и экспоненту _X|
|[isfinite](concurrency-fast-math-namespace-functions.md#isfinite)|Определяет, имеет ли аргумент конечное значение|
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|Определяет, является ли аргумент бесконечности|
|[isnan](concurrency-fast-math-namespace-functions.md#isnan)|Определяет, является ли аргумент значение NaN|
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|Вычисляет действительное число на основе мантиссы и экспоненты|
|[ldexpf](concurrency-fast-math-namespace-functions.md#ldexpf)|Вычисляет действительное число на основе мантиссы и экспоненты|
|[log](concurrency-fast-math-namespace-functions.md#log)|Вычисляет логарифм с основанием e аргумента|
|[log10](concurrency-fast-math-namespace-functions.md#log10)|Вычисляет десятичный логарифм аргумента|
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|Вычисляет десятичный логарифм аргумента|
|[log2](concurrency-fast-math-namespace-functions.md#log2)|Вычисляет логарифм аргумента|
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|Вычисляет логарифм аргумента|
|[logf](concurrency-fast-math-namespace-functions.md#logf)|Вычисляет логарифм с основанием e аргумента|
|[modf](concurrency-fast-math-namespace-functions.md#modf)|Разбивает _X на дробную и целую части.|
|[modff](concurrency-fast-math-namespace-functions.md#modff)|Разбивает _X на дробную и целую части.|
|[pow](concurrency-fast-math-namespace-functions.md#pow)|Возводит _X в степень _Y|
|[powf](concurrency-fast-math-namespace-functions.md#powf)|Возводит _X в степень _Y|
|[round](concurrency-fast-math-namespace-functions.md#round)|Округляет _X до ближайшего целого числа|
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|Округляет _X до ближайшего целого числа|
|[rsqrt](concurrency-fast-math-namespace-functions.md#rsqrt)|Возвращает обратную величину квадратного корня из аргумента|
|[rsqrtf](concurrency-fast-math-namespace-functions.md#rsqrtf)|Возвращает обратную величину квадратного корня из аргумента|
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|Возвращает знак аргумента|
|[signbitf](concurrency-fast-math-namespace-functions.md#signbitf)|Возвращает знак аргумента|
|[sin](concurrency-fast-math-namespace-functions.md#sin)|Вычисляет значение синуса аргумента|
|[sincos](concurrency-fast-math-namespace-functions.md#sincos)|Вычисляет значение синуса и косинуса _X|
|[sincosf](concurrency-fast-math-namespace-functions.md#sincosf)|Вычисляет значение синуса и косинуса _X|
|[sinf](concurrency-fast-math-namespace-functions.md#sinf)|Вычисляет значение синуса аргумента|
|[sinh](concurrency-fast-math-namespace-functions.md#sinh)|Вычисляет значение гиперболического синуса аргумента|
|[sinhf](concurrency-fast-math-namespace-functions.md#sinhf)|Вычисляет значение гиперболического синуса аргумента|
|[sqrt](concurrency-fast-math-namespace-functions.md#sqrt)|Вычисляет квадратный корень аргумента|
|[sqrtf](concurrency-fast-math-namespace-functions.md#sqrtf)|Вычисляет квадратный корень аргумента|
|[tan](concurrency-fast-math-namespace-functions.md#tan)|Вычисляет значение тангенса аргумента|
|[tanf](concurrency-fast-math-namespace-functions.md#tanf)|Вычисляет значение тангенса аргумента|
|[tanh](concurrency-fast-math-namespace-functions.md#tanh)|Вычисляет значение гиперболического тангенса аргумента|
|[tanhf](concurrency-fast-math-namespace-functions.md#tanhf)|Вычисляет значение гиперболического тангенса аргумента|
|[trunc](concurrency-fast-math-namespace-functions.md#trunc)|Усекает аргумент до целой|
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|Усекает аргумент до целой|

## <a name="requirements"></a>Требования

**Заголовок:** amp_math.h

**Пространство имен:** Concurrency::fast_math

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
