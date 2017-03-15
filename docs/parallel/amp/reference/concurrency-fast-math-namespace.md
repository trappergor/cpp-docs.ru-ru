---
title: "Пространство имен Concurrency::fast_math | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 293452bf0a01f7f83a8a41bcb511bc57c9d45f26
ms.lasthandoff: 02/24/2017

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
|[cos функция (fast_math)](concurrency-fast-math-namespace-functions.md#cos)|Вычисляет арккосинус аргумента|  
|[Функция cosf (fast_math)](concurrency-fast-math-namespace-functions.md#cosf)|Вычисляет арккосинус аргумента|  
|[Функция ASIN (fast_math)](concurrency-fast-math-namespace-functions.md#asin)|Вычисляет гиперболический арксинус аргумента|  
|[Функция asinf (fast_math)](concurrency-fast-math-namespace-functions.md#asinf)|Вычисляет гиперболический арксинус аргумента|  
|[Функция ATAN (fast_math)](concurrency-fast-math-namespace-functions.md#atan)|Вычисляет арктангенс аргумента.|  
|[Функция ATAN2 (fast_math)](concurrency-fast-math-namespace-functions.md#atan2)|Вычисляет арктангенс _Y или _X|  
|[Функция atan2f (fast_math)](concurrency-fast-math-namespace-functions.md#atan2f)|Вычисляет арктангенс _Y или _X|  
|[Функция atanf (fast_math)](concurrency-fast-math-namespace-functions.md#atanf)|Вычисляет арктангенс аргумента.|  
|[Функция ceil (fast_math)](concurrency-fast-math-namespace-functions.md#ceil)|Вычисляет ceiling аргумента|  
|[Функция ceilf (fast_math)](concurrency-fast-math-namespace-functions.md#ceilf)|Вычисляет ceiling аргумента|  
|[cos функция (fast_math)](concurrency-fast-math-namespace-functions.md#cos)|Вычисляет косинус аргумента|  
|[Функция cosf (fast_math)](concurrency-fast-math-namespace-functions.md#cosf)|Вычисляет косинус аргумента|  
|[Функция Cosh (fast_math)](concurrency-fast-math-namespace-functions.md#cosh)|Вычисляет гиперболический косинус значение аргумента|  
|[Функция coshf (fast_math)](concurrency-fast-math-namespace-functions.md#coshf)|Вычисляет гиперболический косинус значение аргумента|  
|[Функция EXP (fast_math)](concurrency-fast-math-namespace-functions.md#exp)|Вычисляет экспоненту аргумента base-e|  
|[Функция exp2 (fast_math)](concurrency-fast-math-namespace-functions.md#exp2)|Вычисляет экспоненту аргумента base-2|  
|[Функция exp2f (fast_math)](concurrency-fast-math-namespace-functions.md#exp2f)|Вычисляет экспоненту аргумента base-2|  
|[Функция expf (fast_math)](concurrency-fast-math-namespace-functions.md#expf)|Вычисляет экспоненту аргумента base-e|  
|[Функция fabs (fast_math)](concurrency-fast-math-namespace-functions.md#fabs)|Возвращает абсолютное значение аргумента|  
|[Функция fabsf (fast_math)](concurrency-fast-math-namespace-functions.md#fabsf)|Возвращает абсолютное значение аргумента|  
|[Функция FLOOR (fast_math)](concurrency-fast-math-namespace-functions.md#floor)|Вычисляет floor аргумента|  
|[Функция floorf (fast_math)](concurrency-fast-math-namespace-functions.md#floorf)|Вычисляет floor аргумента|  
|[Функция fmax (fast_math)](concurrency-fast-math-namespace-functions.md#fmax)|Определите максимальное числовое значение аргументов|  
|[Функция fmaxf (fast_math)](concurrency-fast-math-namespace-functions.md#fmaxf)|Определите максимальное числовое значение аргументов|  
|[Функция fmin (fast_math)](concurrency-fast-math-namespace-functions.md#fmin)|Определите минимальное числовое значение аргументов|  
|[Функция fminf (fast_math)](concurrency-fast-math-namespace-functions.md#fminf)|Определите минимальное числовое значение аргументов|  
|[Функция fmod (fast_math)](concurrency-fast-math-namespace-functions.md#fmod)|Вычисляет остаток с плавающей запятой от _X или _Y|  
|[Функция fmodf (fast_math)](concurrency-fast-math-namespace-functions.md#fmodf)|Вычисляет остаток с плавающей запятой от _X или _Y|  
|[Функция frexp (fast_math)](concurrency-fast-math-namespace-functions.md#frexp)|Возвращает мантиссы и экспоненты _X|  
|[Функция frexpf (fast_math)](concurrency-fast-math-namespace-functions.md#frexpf)|Возвращает мантиссы и экспоненты _X|  
|[Функция isFinite (fast_math)](concurrency-fast-math-namespace-functions.md#isfinite)|Определяет, имеет ли аргумент конечное значение|  
|[Функция isinf (fast_math)](concurrency-fast-math-namespace-functions.md#isinf)|Определяет, является ли аргумент бесконечности|  
|[Функция isNaN (fast_math)](concurrency-fast-math-namespace-functions.md#isnan)|Определяет, является ли аргумент значение NaN|  
|[Функция ldexp (fast_math)](concurrency-fast-math-namespace-functions.md#ldexp)|Вычисляет действительное число мантисса и степень|  
|[Функция ldexpf (fast_math)](concurrency-fast-math-namespace-functions.md#ldexpf)|Вычисляет действительное число мантисса и степень|  
|[Функция log (fast_math)](concurrency-fast-math-namespace-functions.md#log)|Вычисляет логарифм аргумента|  
|[Функция LOG10 (fast_math)](concurrency-fast-math-namespace-functions.md#log10)|Вычисляет логарифм по основанию&10; аргумента|  
|[Функция log10f (fast_math)](concurrency-fast-math-namespace-functions.md#log10f)|Вычисляет логарифм по основанию&10; аргумента|  
|[Функция log2 (fast_math)](concurrency-fast-math-namespace-functions.md#log2)|Вычисляет логарифм по основанию&2; аргумента|  
|[Функция log2f (fast_math)](concurrency-fast-math-namespace-functions.md#log2f)|Вычисляет логарифм по основанию&2; аргумента|  
|[Функция logf (fast_math)](concurrency-fast-math-namespace-functions.md#logf)|Вычисляет логарифм аргумента|  
|[Функция modf (fast_math)](concurrency-fast-math-namespace-functions.md#modf)|Разделяет _X в долях и целое число частей.|  
|[Функция modff (fast_math)](concurrency-fast-math-namespace-functions.md#modff)|Разделяет _X в долях и целое число частей.|  
|[pow функция (fast_math)](concurrency-fast-math-namespace-functions.md#pow)|Вычисляет _X, возведенное в степень _Y|  
|[Функция powf (fast_math)](concurrency-fast-math-namespace-functions.md#powf)|Вычисляет _X, возведенное в степень _Y|  
|[Функция Round (fast_math)](concurrency-fast-math-namespace-functions.md#round)|Округляет _X до ближайшего целого числа|  
|[Функция roundf (fast_math)](concurrency-fast-math-namespace-functions.md#roundf)|Округляет _X до ближайшего целого числа|  
|[Функция rsqrt (fast_math)](concurrency-fast-math-namespace-functions.md#rsqrt)|Возвращает обратное квадратного корня аргумент|  
|[Функция rsqrtf (fast_math)](concurrency-fast-math-namespace-functions.md#rsqrtf)|Возвращает обратное квадратного корня аргумент|  
|[Функция signbit (fast_math)](concurrency-fast-math-namespace-functions.md#signbit)|Возвращает знак аргумента|  
|[Функция signbitf (fast_math)](concurrency-fast-math-namespace-functions.md#signbitf)|Возвращает знак аргумента|  
|[Функция sin (fast_math)](concurrency-fast-math-namespace-functions.md#sin)|Вычисляет синус аргумента|  
|[Функция sincos (fast_math)](concurrency-fast-math-namespace-functions.md#sincos)|Вычисляет синус и косинус значение _X|  
|[Функция sincosf (fast_math)](concurrency-fast-math-namespace-functions.md#sincosf)|Вычисляет синус и косинус значение _X|  
|[Функция sinf (fast_math)](concurrency-fast-math-namespace-functions.md#sinf)|Вычисляет синус аргумента|  
|[Функция SINH (fast_math)](concurrency-fast-math-namespace-functions.md#sinh)|Вычисляет гиперболический синус значение аргумента|  
|[Функция sinhf (fast_math)](concurrency-fast-math-namespace-functions.md#sinhf)|Вычисляет гиперболический синус значение аргумента|  
|[Функция SQRT (fast_math)](concurrency-fast-math-namespace-functions.md#sqrt)|Вычисляет квадратный корень аргумента|  
|[Функция sqrtf (fast_math)](concurrency-fast-math-namespace-functions.md#sqrtf)|Вычисляет квадратный корень аргумента|  
|[Функция tan (fast_math)](concurrency-fast-math-namespace-functions.md#tan)|Вычисляет тангенс значение аргумента|  
|[Функция tanf (fast_math)](concurrency-fast-math-namespace-functions.md#tanf)|Вычисляет тангенс значение аргумента|  
|[Функция TANH (fast_math)](concurrency-fast-math-namespace-functions.md#tanh)|Вычисляет гиперболический тангенс значение аргумента|  
|[Функция tanhf (fast_math)](concurrency-fast-math-namespace-functions.md#tanhf)|Вычисляет гиперболический тангенс значение аргумента|  
|[Функция TRUNC (fast_math)](concurrency-fast-math-namespace-functions.md#trunc)|Усекает для целочисленный аргумент|  
|[Функция truncf (fast_math)](concurrency-fast-math-namespace-functions.md#truncf)|Усекает для целочисленный аргумент|  

## <a name="requirements"></a>Требования  
 **Заголовок:** amp_math.h  
  
 **Пространство имен:** Concurrency::fast_math  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

