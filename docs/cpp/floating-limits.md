---
title: "С плавающей запятой ограничения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- float.h header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6406d3d2d81fa3025a024606da68d61b5dcefdb7
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="floating-limits"></a>Пределы констант с плавающей запятой
**Блок, относящийся только к системам Microsoft**  
  
 В следующей таблице представлены ограничения на значения констант с плавающей запятой. Эти ограничения также заданы в стандартном файле заголовка \<float.h >.  
  
### <a name="limits-on-floating-point-constants"></a>Ограничения на константы с плавающей запятой  
  
|Константа|Значение|Значение|  
|--------------|-------------|-----------|  
|FLT_DIG DBL_DIG LDBL_DIG|Количество цифр q, при котором число с плавающей запятой с q десятичными цифрами можно округлить в представление с плавающей запятой и обратно без потери точности.|6 15 15|  
|FLT_EPSILON DBL_EPSILON LDBL_EPSILON|Наименьшее положительное число x, при котором x + 1,0 не равно 1,0.|1.192092896e-07F 2.2204460492503131e-016 2.2204460492503131e-016|  
|FLT_GUARD||0|  
|FLT_MANT_DIG DBL_MANT_DIG LDBL_MANT_DIG|Количество цифр для основания, заданного константой FLT_RADIX, в значащей части числа с плавающей запятой. Основание системы счисления-2; Поэтому эти значения определяют разряды.|24 53 53|  
|FLT_MAX DBL_MAX LDBL_MAX|Максимальное представимое число с плавающей запятой.|3,402823466e+38F 1,7976931348623158e+308 1,7976931348623158e+308|  
|FLT_MAX_10_EXP DBL_MAX_10_EXP LDBL_MAX_10_EXP|Максимальное целое число, таким образом, что 10, возведенное в это число является представимым числом с плавающей запятой.|38 308 308|  
|FLT_MAX_EXP DBL_MAX_EXP LDBL_MAX_EXP|Максимальное целое число, при котором значение FLT_RADIX, возведенное в степень этого числа, является представимым числом с плавающей запятой.|128 1024 1024|  
|FLT_MIN DBL_MIN LDBL_MIN|Минимальное положительное значение.|1.175494351e-38F 2.2250738585072014e-308 2.2250738585072014e-308|  
|FLT_MIN_10_EXP DBL_MIN_10_EXP LDBL_MIN_10_EXP|Минимальное отрицательное целое число, таким образом, что 10, возведенное в это число является представимым числом с плавающей точкой.|-37<br /><br /> -307<br /><br /> -307|  
|FLT_MIN_EXP DBL_MIN_EXP LDBL_MIN_EXP|Минимальное отрицательное целое число, при котором значение FLT_RADIX, возведенное в степень этого числа, является представимым числом с плавающей запятой.|-125<br /><br /> -1021<br /><br /> -1021|  
|FLT_NORMALIZE||0|  
|FLT_RADIX _DBL_RADIX _LDBL_RADIX|Основание экспоненциальной формы представления.|2 2 2|  
|FLT_ROUNDS _DBL_ROUNDS _LDBL_ROUNDS|Режим округления для сложения чисел с плавающей запятой.|1 (ближайшее) 1 (ближайшее) 1 (ближайшее)|  
  
> [!NOTE]
>  В будущих версиях продукта информация из приведенной выше таблицы может отличаться.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Пределы целых чисел](../cpp/integer-limits.md)