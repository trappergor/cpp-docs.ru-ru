---
title: Константы типов данных | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- FLT_MIN
- SHRT_MAX
- CHAR_MIN
- MB_LEN_MAX
- DBL_EPSILON
- SHRT_MIN
- _FLT_RADIX
- FLT_DIG
- FLT_MAX_10_EXP
- FLT_MANT_DIG
- DBL_MAX_EXP
- SCHAR_MIN
- SCHAR_MAX
- DBL_MIN
- FLT_MIN_10_EXP
- _DBL_ROUNDS
- USHRT_MAX
- FLT_MAX_EXP
- LONG_MAX
- DBL_MAX
- DBL_DIG
- FLT_MIN_EXP
- INT_MIN
- DBL_MIN_10_EXP
- CHAR_BIT
- INT_MAX
- ULONG_MAX
- DBL_MIN_EXP
- LONG_MIN
- _FLT_ROUNDS
- DBL_MANT_DIG
- _DBL_RADIX
- CHAR_MAX
- FLT_MAX
- DBL_MAX_10_EXP
- UCHAR_MAX
- FLT_EPSILON
- UINT_MAX
dev_langs:
- C++
helpviewer_keywords:
- DBL_MAX_EXP constant
- _DBL_RADIX constant
- FLT_MIN_EXP constant
- DBL_EPSILON constant
- INT_MIN constant
- FLT_EPSILON constant
- DBL_MANT_DIG constant
- _FLT_RADIX constant
- DBL_MIN constant
- USHRT_MAX constant
- FLT_MAX_10_EXP constant
- _FLT_ROUNDS constant
- data type constants [C++]
- _DBL_ROUNDS constant
- CHAR_MAX constant
- FLT_MAX_EXP constant
- FLT_MIN constant
- CHAR_MIN constant
- FLT_MIN_10_EXP constant
- DBL_MIN_EXP constant
- SCHAR_MAX constant
- FLT_RADIX constant
- CHAR_BIT constant
- UCHAR_MAX constant
- DBL_RADIX constant
- FLT_ROUNDS constant
- LONG_MIN constant
- SHRT_MAX constant
- LONG_MAX constant
- DBL_MAX_10_EXP constant
- DBL_MIN_10_EXP constant
- INT_MAX constant
- constants [C++], data type
- ULONG_MAX constant
- FLT_DIG constant
- MB_LEN_MAX constant
- DBL_DIG constant
- SHRT_MIN constant
- DBL_MAX constant
- DBL_ROUNDS constant
- FLT_MAX constant
- UINT_MAX constant
- FLT_MANT_DIG constant
- SCHAR_MIN constant
ms.assetid: c0f1c405-0465-41d5-b5ff-e81cdb6f1622
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf9a64b81ae90c517e9cd15e796dfb1333c7b08c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="data-type-constants"></a>Константы типа данных
Константы типа данных — это зависящие от реализации диапазоны значений, допустимые для целочисленных типов данных. Перечисленные ниже константы задают диапазоны для целочисленных типов данных и определяются в разделе LIMITS.H.  
  
> [!NOTE]
>  Параметр компилятора /J указывает, что вместо `char` по умолчанию будет использоваться тип `unsigned`.  
  
|Константа|Значение|Значение|  
|--------------|-----------|-------------|  
|**SCHAR_MAX**|127|Максимальное значение для `char` со знаком|  
|**SCHAR_MIN**|–128|Минимальное значение для `char` со знаком|  
|**UCHAR_MAX**|255 (0xff)|Максимальное значение для `unsigned char`|  
|**CHAR_BIT**|8|Число бит для `char`|  
|**USHRT_MAX**|65 535 (0xffff)|Максимальное значение для **unsigned short**|  
|**SHRT_MAX**|32767|Максимальное значение для **short** (со знаком)|  
|**SHRT_MIN**|-32768|Минимальное значение для **short** (со знаком)|  
|**UINT_MAX**|4 294 967 295 (0xffffffff)|Максимальное значение для `unsigned int`|  
|**ULONG_MAX**|4 294 967 295 (0xffffffff)|Максимальное значение для `unsigned long`|  
|**INT_MAX**|2147483647|Максимальное значение для `int` (со знаком)|  
|**INT_MIN**|-2147483647-1|Минимальное значение для `int` (со знаком)|  
|**LONG_MAX**|2147483647|Максимальное значение для **long** (со знаком)|  
|**LONG_MIN**|-2147483647-1|Минимальное значение для **long** (со знаком)|  
|**CHAR_MAX**|127 (или 255, если используется параметр /J)|Максимальное значение для `char`|  
|**CHAR_MIN**|–128 (или 0, если используется параметр /J)|Минимальное значение для `char`|  
|**MB_LEN_MAX**|2|Максимальное число байтов для многобайтового `char`|  
|**_I64_MAX**|9223372036854775807|Максимальное значение для __**int64** (со знаком)|  
|**_I64_MIN**|-9223372036854775807-1|Минимальное значение для __**int64** (со знаком)|  
|**_UI64_MAX**|0×FFFFFFFFFFFFFFFF|Минимальное значение для __**int64** (без знака)|  
  
 Следующие константы указывают диапазон и другие характеристики для типов данных **double** и **float**, и определяются в разделе FLOAT.H  
  
|Константа|Значение|Описание:|  
|--------------|-----------|-----------------|  
|**DBL_DIG**|15|Количество десятичных разрядов точности|  
|**DBL_EPSILON**|2,2204460492503131e-016|Наименьшее значение, при котором 1,0 +**DBL_EPSILON** ! = 1,0|  
|**DBL_MANT_DIG**|53|Число бит в мантиссе|  
|**DBL_MAX**|1,7976931348623158e+308|Максимальное значение|  
|**DBL_MAX_10_EXP**|308|Максимальный показатель десятичной степени|  
|**DBL_MAX_EXP**|1024|Максимальный показатель двоичной степени|  
|**DBL_MIN**|2,2250738585072014e-308|Минимальное положительное значение|  
|**DBL_MIN_10_EXP**|(-307)|Минимальный показатель десятичной степени|  
|**DBL_MIN_EXP**|(-1021)|Минимальный показатель двоичной степени|  
|**_DBL_RADIX**|2|Основание системы счисления|  
|**_DBL_ROUNDS**|1|Округление при сложении: near|  
|**FLT_DIG**|6|Число десятичных разрядов точности|  
|**FLT_EPSILON**|1,192092896e-07F|Наименьшее значение, при котором 1,0 +**FLT_EPSILON** ! = 1,0|  
|**FLT_MANT_DIG**|24|Число бит в мантиссе|  
|**FLT_MAX**|3,402823466e+38F|Максимальное значение|  
|**FLT_MAX_10_EXP**|38|Максимальный показатель десятичной степени|  
|**FLT_MAX_EXP**|128|Максимальный показатель двоичной степени|  
|**FLT_MIN**|1,175494351e-38F|Минимальное положительное значение|  
|**FLT_MIN_10_EXP**|(-37)|Минимальный показатель десятичной степени|  
|**FLT_MIN_EXP**|(-125)|Минимальный показатель двоичной степени|  
|**FLT_RADIX**|2|Основание системы счисления|  
|**FLT_ROUNDS**|1|Округление при сложении: near|  
  
## <a name="see-also"></a>См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)