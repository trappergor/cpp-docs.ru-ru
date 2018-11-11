---
title: Константы типа данных
ms.date: 06/25/2018
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
- LLONG_MIN
- LLONG_MAX
- ULLONG_MAX
- _I8_MIN
- _I8_MAX
- _UI8_MAX
- _I16_MIN
- _I16_MAX
- _UI16_MAX
- _I32_MIN
- _I32_MAX
- _UI32_MAX
- _I64_MIN
- _I64_MAX
- _UI64_MAX
- _I128_MIN
- _I128_MAX
- _UI128_MAX
- SIZE_MAX
- RSIZE_MAX
- LDBL_DIG
- LDBL_EPSILON
- LDBL_HAS_SUBNORM
- LDBL_MANT_DIG
- LDBL_MAX
- LDBL_MAX_10_EXP
- LDBL_MAX_EXP
- LDBL_MIN
- LDBL_MIN_10_EXP
- LDBL_MIN_EXP
- _LDBL_RADIX
- LDBL_TRUE_MIN
- DECIMAL_DIG
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
- LLONG_MIN constant
- LLONG_MAX constant
- ULLONG_MAX constant
- _I8_MIN constant
- _I8_MAX constant
- _UI8_MAX constant
- _I16_MIN constant
- _I16_MAX constant
- _UI16_MAX constant
- _I32_MIN constant
- _I32_MAX constant
- _UI32_MAX constant
- _I64_MIN constant
- _I64_MAX constant
- _UI64_MAX constant
- _I128_MIN constant
- _I128_MAX constant
- _UI128_MAX constant
- SIZE_MAX constant
- RSIZE_MAX constant
ms.assetid: c0f1c405-0465-41d5-b5ff-e81cdb6f1622
ms.openlocfilehash: c4ffbf294083131f29ffe957fd0434182fbb8f99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636934"
---
# <a name="data-type-constants"></a>Константы типа данных

Константы типа данных — это зависящие от реализации диапазоны значений, допустимые для целочисленных типов данных и типов данных с плавающей запятой.

## <a name="integral-type-constants"></a>Константы целочисленных типов

Эти константы предоставляют диапазоны значений для целочисленных типов данных. Чтобы использовать их, включите заголовок limits.h в исходный файл.

```C
#include <limits.h>
```

> [!NOTE]
> Параметр компилятора [/J](../build/reference/j-default-char-type-is-unsigned.md) указывает, что вместо **char** по умолчанию будет использоваться тип **unsigned**.

|Константа|Значение|Описание:|
|--------------|-----------|-------------|
|**CHAR_BIT**|8|Число битов в **char**|
|**SCHAR_MIN**|(–128)|Минимальное значение signed **char**|
|**SCHAR_MAX**|127|Максимальное значение signed **char**|
|**UCHAR_MAX**|255 (0xff)|Максимальное значение **unsigned** **char**|
|**CHAR_MIN**|(–128) (или 0, если используется параметр **/J**)|Минимальное значение **char**|
|**CHAR_MAX**|127 (или 255, если используется параметр **/J**)|Максимальное значение **char**|
|**MB_LEN_MAX**|5|Максимальное число байт многобайтового **char**|
|**SHRT_MIN**|-32768|Минимальное значение signed **short**|
|**SHRT_MAX**|32767|Максимальное значение signed **short**|
|**USHRT_MAX**|65 535 (0xffff)|Максимальное значение **unsigned** **short**|
|**INT_MIN**|(–2 147 483 647 – 1)|Минимальное значение signed **int**|
|**INT_MAX**|2147483647|Максимальное значение signed **int**|
|**UINT_MAX**|4 294 967 295 (0xffffffff)|Максимальное значение **unsigned** **int**|
|**LONG_MIN**|(–2 147 483 647L – 1)|Минимальное значение signed **long**|
|**LONG_MAX**|2 147 483 647L|Максимальное значение signed **long**|
|**ULONG_MAX**|4 294 967 295UL (0xfffffffful)|Максимальное значение **unsigned** **long**|
|**LLONG_MIN**|(–9 223 372 036 854 775 807LL – 1)|Минимальное значение signed **long** **long** или **__int64**|
|**LLONG_MAX**|9 223 372 036 854 775 807LL|Максимальное значение signed **long** **long** или **__int64**|
|**ULLONG_MAX**|0xffffffffffffffffull|Максимальное значение **unsigned** **long** **long**|
|**_I8_MIN**|(–127i8 – 1)|Минимальное 8-битное значение со знаком|
|**_I8_MAX**|127i8|Максимальное 8-битное значение со знаком|
|**_UI8_MAX**|0xffui8|Максимальное 8-битное значение без знака|
|**_I16_MIN**|(–32 767i16 – 1)|Минимальное 16-битное значение со знаком|
|**_I16_MAX**|32 767i16|Максимальное 16-битное значение со знаком|
|**_UI16_MAX**|0xffffui16|Максимальное 16-битное значение без знака|
|**_I32_MIN**|(–2 147 483 647i32 – 1)|Минимальное 32-битное значение со знаком|
|**_I32_MAX**|2 147 483 647i32|Максимальное 32-битное значение со знаком|
|**_UI32_MAX**|0xffffffffui32|Максимальное 32-битное значение без знака|
|**_I64_MIN**|(–9 223 372 036 854 775 807 – 1)|Минимальное 64-битное значение со знаком|
|**_I64_MAX**|9223372036854775807|Максимальное 64-битное значение со знаком|
|**_UI64_MAX**|0xffffffffffffffffui64|Максимальное 64-битное значение без знака|
|**_I128_MIN**|(–170 141 183 460 469 231 731 687 303 715 884 105 727i128 – 1)|Минимальное 128-битное значение со знаком|
|**_I128_MAX**|170 141 183 460 469 231 731 687 303 715 884 105 727i128|Максимальное 128-битное значение со знаком|
|**_UI128_MAX**|0xffffffffffffffffffffffffffffffffui128|Максимальное 128-битное значение без знака|
|**SIZE_MAX**|совпадает с **_UI64_MAX**, если задано значение **_WIN64**, или **UINT_MAX**|Максимальный размер собственного целочисленного типа|
|**RSIZE_MAX**|совпадает с (**SIZE_MAX** >> 1)|Максимальный размер целочисленного типа защищенной библиотеки|

## <a name="floating-point-type-constants"></a>Типы констант с плавающей запятой

Следующие константы указывают диапазон и другие характеристики для типов данных **long** **double**, **double** и **float**. Чтобы использовать их, включите заголовок float.h в исходный файл.

```C
#include <float.h>
```

|Константа|Значение|Описание:|
|--------------|-----------|-----------------|
|**DBL_DECIMAL_DIG**|17|Число десятичных разрядов точности округления|
|**DBL_DIG**|15|Количество десятичных разрядов точности|
|**DBL_EPSILON**|2,2204460492503131e-016|Наименьшее значение, при котором 1.0 + **DBL_EPSILON** != 1.0|
|**DBL_HAS_SUBNORM**|1|Тип поддерживает денормализованные числа|
|**DBL_MANT_DIG**|53|Число битов в мантиссе|
|**DBL_MAX**|1,7976931348623158e+308|Максимальное значение|
|**DBL_MAX_10_EXP**|308|Максимальный показатель десятичной степени|
|**DBL_MAX_EXP**|1024|Максимальный показатель двоичной степени|
|**DBL_MIN**|2,2250738585072014e-308|Минимальное нормализованное положительное значение|
|**DBL_MIN_10_EXP**|(-307)|Минимальный показатель десятичной степени|
|**DBL_MIN_EXP**|(-1021)|Минимальный показатель двоичной степени|
|**_DBL_RADIX**|2|Основание системы счисления|
|**DBL_TRUE_MIN**|4.9406564584124654e-324|Минимальное денормализованное положительное значение|
|**FLT_DECIMAL_DIG**|9|Число десятичных разрядов точности округления|
|**FLT_DIG**|6|Число десятичных разрядов точности|
|**FLT_EPSILON**|1,192092896e-07F|Наименьшее значение, при котором 1.0 + **FLT_EPSILON** != 1.0|
|**FLT_HAS_SUBNORM**|1|Тип поддерживает денормализованные числа|
|**FLT_MANT_DIG**|24|Число битов в мантиссе|
|**FLT_MAX**|3,402823466e+38F|Максимальное значение|
|**FLT_MAX_10_EXP**|38|Максимальный показатель десятичной степени|
|**FLT_MAX_EXP**|128|Максимальный показатель двоичной степени|
|**FLT_MIN**|1,175494351e-38F|Минимальное нормализованное положительное значение|
|**FLT_MIN_10_EXP**|(-37)|Минимальный показатель десятичной степени|
|**FLT_MIN_EXP**|(-125)|Минимальный показатель двоичной степени|
|**FLT_RADIX**|2|Основание системы счисления|
|**FLT_TRUE_MIN**|1.401298464e-45F|Минимальное денормализованное положительное значение|
|**LDBL_DIG**|15|Количество десятичных разрядов точности|
|**LDBL_EPSILON**|2,2204460492503131e-016|Наименьшее значение, при котором 1.0 + **LDBL_EPSILON** != 1.0|
|**LDBL_HAS_SUBNORM**|1|Тип поддерживает денормализованные числа|
|**LDBL_MANT_DIG**|53|Число битов в мантиссе|
|**LDBL_MAX**|1,7976931348623158e+308|Максимальное значение|
|**LDBL_MAX_10_EXP**|308|Максимальный показатель десятичной степени|
|**LDBL_MAX_EXP**|1024|Максимальный показатель двоичной степени|
|**LDBL_MIN**|2,2250738585072014e-308|Минимальное нормализованное положительное значение|
|**LDBL_MIN_10_EXP**|(-307)|Минимальный показатель десятичной степени|
|**LDBL_MIN_EXP**|(-1021)|Минимальный показатель двоичной степени|
|**_LDBL_RADIX**|2|Основание системы счисления|
|**LDBL_TRUE_MIN**|4.9406564584124654e-324|Минимальное денормализованное положительное значение|
|**DECIMAL_DIG**|совпадает с **DBL_DECIMAL_DIG**|Число десятичных разрядов точности округления по умолчанию (два)|

## <a name="see-also"></a>См. также

[Глобальные константы](../c-runtime-library/global-constants.md)
