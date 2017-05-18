---
title: "Пространство имен Concurrency::fast_math | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::fast_math
dev_langs:
- C++
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d8a94b0911b772f4972416722757bec24a4826ed
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="concurrencyfastmath-namespace"></a>Пространство имен Concurrency::fast_math
Функции в `fast_math` пространство имен имеет точность ниже, поддерживают только одинарной точности (`float`) и вызывать встроенные функции DirectX. Существуют две версии каждой функции, например `cos` и `cosf`. Обе версии, принимающие и возвращающие `float`, однако каждый вызов же DirectX встроенная функция.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace fast_math;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|Вычисляет арккосинус аргумента|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|Вычисляет арккосинус аргумента|  
|[asin](concurrency-fast-math-namespace-functions.md#asin)|Вычисляет гиперболический арксинус аргумента|  
|[asinf](concurrency-fast-math-namespace-functions.md#asinf)|Вычисляет гиперболический арксинус аргумента|  
|[atan](concurrency-fast-math-namespace-functions.md#atan)|Вычисляет арктангенс аргумента.|  
|[atan2](concurrency-fast-math-namespace-functions.md#atan2)|Вычисляет арктангенс _Y или _X|  
|[atan2f](concurrency-fast-math-namespace-functions.md#atan2f)|Вычисляет арктангенс _Y или _X|  
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
|[fmod](concurrency-fast-math-namespace-functions.md#fmod)|Вычисляет остаток с плавающей запятой от _X или _Y|  
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|Вычисляет остаток с плавающей запятой от _X или _Y|  
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|Возвращает мантиссы и экспоненты _X|  
|[frexpf](concurrency-fast-math-namespace-functions.md#frexpf)|Возвращает мантиссы и экспоненты _X|  
|[isFinite](concurrency-fast-math-namespace-functions.md#isfinite)|Определяет, имеет ли аргумент конечное значение|  
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|Определяет, является ли аргумент бесконечности|  
|[isnan](concurrency-fast-math-namespace-functions.md#isnan)|Определяет, является ли аргумент значение NaN|  
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|Вычисляет действительное число мантисса и степень|  
|[ldexpf](concurrency-fast-math-namespace-functions.md#ldexpf)|Вычисляет действительное число мантисса и степень|  
|[log](concurrency-fast-math-namespace-functions.md#log)|Вычисляет логарифм аргумента|  
|[log10](concurrency-fast-math-namespace-functions.md#log10)|Вычисляет логарифм по основанию&10; аргумента|  
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|Вычисляет логарифм по основанию&10; аргумента|  
|[log2](concurrency-fast-math-namespace-functions.md#log2)|Вычисляет логарифм по основанию&2; аргумента|  
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|Вычисляет логарифм по основанию&2; аргумента|  
|[logf](concurrency-fast-math-namespace-functions.md#logf)|Вычисляет логарифм аргумента|  
|[modf](concurrency-fast-math-namespace-functions.md#modf)|Разделяет _X в долях и целое число частей.|  
|[modff](concurrency-fast-math-namespace-functions.md#modff)|Разделяет _X в долях и целое число частей.|  
|[pow](concurrency-fast-math-namespace-functions.md#pow)|Вычисляет _X, возведенное в степень _Y|  
|[powf](concurrency-fast-math-namespace-functions.md#powf)|Вычисляет _X, возведенное в степень _Y|  
|[round](concurrency-fast-math-namespace-functions.md#round)|Округляет _X до ближайшего целого числа|  
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|Округляет _X до ближайшего целого числа|  
|[rsqrt](concurrency-fast-math-namespace-functions.md#rsqrt)|Возвращает обратное квадратного корня аргумент|  
|[rsqrtf](concurrency-fast-math-namespace-functions.md#rsqrtf)|Возвращает обратное квадратного корня аргумент|  
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|Возвращает знак аргумента|  
|[signbitf](concurrency-fast-math-namespace-functions.md#signbitf)|Возвращает знак аргумента|  
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
|[trunc](concurrency-fast-math-namespace-functions.md#trunc)|Усекает для целочисленный аргумент|  
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|Усекает для целочисленный аргумент|  

## <a name="requirements"></a>Требования  
 **Заголовок:** amp_math.h  
  
 **Пространство имен:** Concurrency::fast_math  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

