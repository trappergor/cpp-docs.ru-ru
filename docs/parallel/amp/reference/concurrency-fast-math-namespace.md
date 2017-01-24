---
title: "Пространство имен Concurrency::fast_math | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_math/Concurrency::fast_math"
dev_langs: 
  - "C++"
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: 9
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пространство имен Concurrency::fast_math
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Функции, находящиеся в пространстве имен `fast_math`, имеют более низкую точность, поддерживают только одиночную точность\(`float`\) и вызывают встроенные функции DirectX.  Для каждой функции существует две версии, например `cos` и `cosf`.  Обе версии принимают и возвращают `float`, но каждая из них вызывает одну и ту же внутреннюю функцию DirectX.  
  
## Синтаксис  
  
```  
namespace fast_math;  
```  
  
## Члены  
  
### Функции  
  
|Name|Описание|  
|----------|--------------|  
|[Функция cos \(fast\_math\)](../Topic/cos%20Function%20%20\(fast_math\).md)|Вычисляет арккосинус аргумента|  
|[Функция cosf \(fast\_math\)](../Topic/cosf%20Function%20\(fast_math\).md)|Вычисляет арккосинус аргумента|  
|[Функция asin \(fast\_math\)](../Topic/asin%20Function%20\(fast_math\).md)|Вычисляет арксинус аргумента|  
|[Функция asinf \(fast\_math\)](../Topic/asinf%20Function%20\(fast_math\).md)|Вычисляет арксинус аргумента|  
|[Функция atan \(fast\_math\)](../Topic/atan%20Function%20\(fast_math\).md)|Вычисляет арктангенс аргумента|  
|[Функция atan2 \(fast\_math\)](../Topic/atan2%20Function%20\(fast_math\).md)|Вычисляет арктангенс \_Y\/\_X|  
|[Функция atan2f \(fast\_math\)](../Topic/atan2f%20Function%20\(fast_math\).md)|Вычисляет арктангенс \_Y\/\_X|  
|[Функция atanf \(fast\_math\)](../Topic/atanf%20Function%20\(fast_math\).md)|Вычисляет арктангенс аргумента|  
|[Функция ceil \(fast\_math\)](../Topic/ceil%20Function%20\(fast_math\).md)|Вычисляет максимальное значение аргумента|  
|[Функция ceilf \(fast\_math\)](../Topic/ceilf%20Function%20\(fast_math\).md)|Вычисляет максимальное значение аргумента|  
|[Функция cos \(fast\_math\)](../Topic/cos%20Function%20%20\(fast_math\).md)|Вычисляет косинус аргумента|  
|[Функция cosf \(fast\_math\)](../Topic/cosf%20Function%20\(fast_math\).md)|Вычисляет косинус аргумента|  
|[Функция cosh \(fast\_math\)](../Topic/cosh%20Function%20\(fast_math\).md)|Вычисляет значение гиперболического косинуса аргумента|  
|[Функция coshf \(fast\_math\)](../Topic/coshf%20Function%20\(fast_math\).md)|Вычисляет значение гиперболического косинуса аргумента|  
|[Функция exp \(fast\_math\)](../Topic/exp%20Function%20\(fast_math\).md)|Вычисляет экспоненту аргумента с основанием e|  
|[Функция exp2 \(fast\_math\)](../Topic/exp2%20Function%20\(fast_math\).md)|Вычисляет экспоненту аргумента с основанием 2|  
|[Функция exp2f \(fast\_math\)](../Topic/exp2f%20Function%20\(fast_math\).md)|Вычисляет экспоненту аргумента с основанием 2|  
|[Функция expf \(fast\_math\)](../Topic/expf%20Function%20\(fast_math\).md)|Вычисляет экспоненту аргумента с основанием e|  
|[Функция fabs \(fast\_math\)](../Topic/fabs%20Function%20\(fast_math\).md)|Возвращает абсолютное значение аргумента|  
|[Функция fabsf \(fast\_math\)](../Topic/fabsf%20Function%20\(fast_math\).md)|Возвращает абсолютное значение аргумента|  
|[Функция floor \(fast\_math\)](../Topic/floor%20Function%20\(fast_math\).md)|Вычисляет минимальное значение аргумента|  
|[Функция floorf \(fast\_math\)](../Topic/floorf%20Function%20\(fast_math\).md)|Вычисляет минимальное значение аргумента|  
|[Функция fmax \(fast\_math\)](../Topic/fmax%20Function%20\(fast_math\).md)|Определение максимального числового значения аргументов|  
|[Функция fmaxf \(fast\_math\)](../Topic/fmaxf%20Function%20\(fast_math\).md)|Определение максимального числового значения аргументов|  
|[Функция fmin \(fast\_math\)](../Topic/fmin%20Function%20\(fast_math\).md)|Определение минимального числового значения аргументов|  
|[Функция fminf \(fast\_math\)](../Topic/fminf%20Function%20\(fast_math\).md)|Определение минимального числового значения аргументов|  
|[Функция fmod \(fast\_math\)](../Topic/fmod%20Function%20\(fast_math\).md)|Вычисляет остаток от деления \_X\/\_Y с плавающей точкой|  
|[Функция fmodf \(fast\_math\)](../Topic/fmodf%20Function%20\(fast_math\).md)|Вычисляет остаток от деления \_X\/\_Y с плавающей точкой|  
|[Функция frexp \(fast\_math\)](../Topic/frexp%20Function%20\(fast_math\).md)|Получает мантиссу и экспоненту \_X|  
|[Функция frexpf \(fast\_math\)](../Topic/frexpf%20Function%20\(fast_math\).md)|Получает мантиссу и экспоненту \_X|  
|[Функция isfinite \(fast\_math\)](../Topic/isfinite%20Function%20\(fast_math\).md)|Определяет, имеет ли аргумент конечное значение|  
|[Функция isinf \(fast\_math\)](../Topic/isinf%20Function%20\(fast_math\).md)|Определяет, равен ли аргумент бесконечности|  
|[Функция isnan \(fast\_math\)](../Topic/isnan%20Function%20\(fast_math\).md)|Определяет, является ли аргумент нечисловым|  
|[Функция ldexp \(fast\_math\)](../Topic/ldexp%20Function%20\(fast_math\).md)|Вычисляет действительное число на основе мантиссы и экспоненты|  
|[Функция ldexpf \(fast\_math\)](../Topic/ldexpf%20Function%20\(fast_math\).md)|Вычисляет действительное число на основе мантиссы и экспоненты|  
|[Функция log \(fast\_math\)](../Topic/log%20Function%20\(fast_math\).md)|Вычисляет натуральный логарифм аргумента|  
|[Функция log10 \(fast\_math\)](../Topic/log10%20Function%20\(fast_math\).md)|Вычисляет десятичный логарифм аргумента|  
|[Функция log10f \(fast\_math\)](../Topic/log10f%20Function%20\(fast_math\).md)|Вычисляет десятичный логарифм аргумента|  
|[Функция log2 \(fast\_math\)](../Topic/log2%20Function%20\(fast_math\).md)|Вычисляет двоичный логарифм аргумента|  
|[Функция log2f \(fast\_math\)](../Topic/log2f%20Function%20\(fast_math\).md)|Вычисляет двоичный логарифм аргумента|  
|[Функция logf \(fast\_math\)](../Topic/logf%20Function%20\(fast_math\).md)|Вычисляет натуральный логарифм аргумента|  
|[Функция modf \(fast\_math\)](../Topic/modf%20Function%20\(fast_math\).md)|Разбивает \_X на дробную и целую части.|  
|[Функция modff \(fast\_math\)](../Topic/modff%20Function%20\(fast_math\).md)|Разбивает \_X на дробную и целую части.|  
|[Функция pow \(fast\_math\)](../Topic/pow%20Function%20\(fast_math\).md)|Возводит \_X в степень \_Y|  
|[Функция powf \(fast\_math\)](../Topic/powf%20Function%20\(fast_math\).md)|Возводит \_X в степень \_Y|  
|[Функция round \(fast\_math\)](../Topic/round%20Function%20\(fast_math\).md)|Округляет \_X до ближайшего целого числа|  
|[Функция roundf \(fast\_math\)](../Topic/roundf%20Function%20\(fast_math\).md)|Округляет \_X до ближайшего целого числа|  
|[Функция rsqrt \(fast\_math\)](../Topic/rsqrt%20Function%20\(fast_math\).md)|Возвращает обратную величину квадратного корня из аргумента|  
|[Функция rsqrtf \(fast\_math\)](../Topic/rsqrtf%20Function%20\(fast_math\).md)|Возвращает обратную величину квадратного корня из аргумента|  
|[Функция signbit \(fast\_math\)](../Topic/signbit%20Function%20\(fast_math\).md)|Возвращает знак аргумента|  
|[Функция signbitf \(fast\_math\)](../Topic/signbitf%20Function%20\(fast_math\).md)|Возвращает знак аргумента|  
|[Функция sin \(fast\_math\)](../Topic/sin%20Function%20\(fast_math\).md)|Вычисляет значение синуса аргумента|  
|[Функция sincos \(fast\_math\)](../Topic/sincos%20Function%20\(fast_math\).md)|Вычисляет значение синуса и косинуса \_X|  
|[Функция sincosf \(fast\_math\)](../Topic/sincosf%20Function%20\(fast_math\).md)|Вычисляет значение синуса и косинуса \_X|  
|[Функция sinf \(fast\_math\)](../Topic/sinf%20Function%20\(fast_math\).md)|Вычисляет значение синуса аргумента|  
|[Функция sinh \(fast\_math\)](../Topic/sinh%20Function%20\(fast_math\).md)|Вычисляет значение гиперболического синуса аргумента|  
|[Функция sinhf \(fast\_math\)](../Topic/sinhf%20Function%20\(fast_math\).md)|Вычисляет значение гиперболического синуса аргумента|  
|[Функция sqrt \(fast\_math\)](../Topic/sqrt%20Function%20\(fast_math\).md)|Вычисляет квадратный корень аргумента|  
|[Функция sqrtf \(fast\_math\)](../Topic/sqrtf%20Function%20\(fast_math\).md)|Вычисляет квадратный корень аргумента|  
|[Функция tan \(fast\_math\)](../Topic/tan%20Function%20\(fast_math\).md)|Вычисляет значение тангенса аргумента|  
|[Функция tanf \(fast\_math\)](../Topic/tanf%20Function%20\(fast_math\).md)|Вычисляет значение тангенса аргумента|  
|[Функция tanh \(fast\_math\)](../Topic/tanh%20Function%20\(fast_math\).md)|Вычисляет значение гиперболического тангенса аргумента|  
|[Функция tanhf \(fast\_math\)](../Topic/tanhf%20Function%20\(fast_math\).md)|Вычисляет значение гиперболического тангенса аргумента|  
|[Функция trunc \(fast\_math\)](../Topic/trunc%20Function%20\(fast_math\).md)|Усекает аргумент до целой части|  
|[Функция truncf \(fast\_math\)](../Topic/truncf%20Function%20\(fast_math\).md)|Усекает аргумент до целой части|  
  
## Требования  
 **Заголовок:** amp\_math.h  
  
 **Пространство имен:** Concurrency::fast\_math  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)