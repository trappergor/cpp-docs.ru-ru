---
title: abs, labs, llabs, _abs64
description: Справочник по API для ABS, Labs, ллабс и _abs64; , который вычисляет абсолютное значение значения.
ms.date: 04/05/2018
api_name:
- abs
- _abs64
- labs
- llabs
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- stdlib/_abs64
- math/abs
- _abs64
- abs
- labs
- math/labs
- llabs
- math/llabs
- cmath/abs
helpviewer_keywords:
- absolute values
- abs function
- abs64 function
- _abs64 function
- calculating absolute values
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
ms.openlocfilehash: 4527950e4f5577b9285d12309742accb64b9a24a
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556753"
---
# <a name="abs-labs-llabs-_abs64"></a>abs, labs, llabs, _abs64

Вычисляет абсолютное значение аргумента.

## <a name="syntax"></a>Синтаксис

```C
int abs( int n );
long labs( long n );
long long llabs( long long n );
__int64 _abs64( __int64 n );
```

```cpp
long abs( long n );   // C++ only
long long abs( long long n );   // C++ only
double abs( double n );   // C++ only
long double abs( long double n );   // C++ only
float abs( float n );   // C++ only
```

### <a name="parameters"></a>Параметры

*\n*\
Числовое значение.

## <a name="return-value"></a>Возвращаемое значение

Функции **ABS**, **Labs**, **ллабс**и **_abs64** возвращают абсолютное значение параметра *n*. Ошибки не возвращаются.

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **ABS** , которые принимают и возвращают **`long`** значения,,, **`long long`** **`float`** **`double`** и **`long double`** . Эти перегрузки определены в \<cmath> заголовке. В программе на языке **ABS** всегда принимает и возвращает **`int`** .

**Конкретно для Майкрософт**. Поскольку диапазон отрицательных целых чисел, которые могут быть представлены с помощью любого целочисленного типа, больше, чем диапазон положительных целых чисел, которые могут быть представлены с помощью этого типа, можно указать аргумент для этих функций, которые невозможно преобразовать. Если абсолютное значение аргумента не может быть представлено типом возвращаемого значения, функции **ABS** возвращают значение аргумента без изменений. В частности `abs(INT_MIN)` возвращает `INT_MIN`, `labs(LONG_MIN)` возвращает `LONG_MIN`, `llabs(LLONG_MIN)` возвращает `LLONG_MIN`, а `_abs64(_I64_MIN)` возвращает `_I64_MIN`. Это означает, что функции **ABS** нельзя использовать для гарантии положительного значения.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|-----------------------|---------------------------|
|**ABS**, **Labs**, **ллабс**|\<math.h> или \<stdlib.h>|\<cmath>, \<cstdlib>, \<stdlib.h> или \<math.h>|
|**_abs64**|\<stdlib.h>|\<cstdlib> или \<stdlib.h>|

Чтобы использовать перегруженные версии **ABS** в C++, необходимо включить \<cmath> заголовок.

## <a name="example"></a>Пример

Эта программа вычисляет и отображает абсолютные значения несколько чисел.

```C
// crt_abs.c
// Build: cl /W3 /TC crt_abs.c
// This program demonstrates the use of the abs function
// by computing and displaying the absolute values of
// several numbers.

#include <stdio.h>
#include <math.h>
#include <stdlib.h>
#include <limits.h>

int main( void )
{
    int ix = -4;
    long lx = -41567L;
    long long llx = -9876543210LL;
    __int64 wx = -1;

    // absolute 32 bit integer value
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));

    // absolute long integer value
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));

    // absolute long long integer value
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));

    // absolute 64 bit integer value
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,
        _abs64(wx));

    // Integer error cases:
    printf_s("Microsoft implementation-specific results:\n");
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));
}
```

```Output
The absolute value of -4 is 4
The absolute value of -41567 is 41567
The absolute value of -9876543210 is 9876543210
The absolute value of 0xffffffffffffffff is 0x0000000000000001
Microsoft implementation-specific results:
abs(INT_MIN) returns -2147483648
labs(LONG_MIN) returns -2147483648
llabs(LLONG_MIN) returns -9223372036854775808
_abs64(_I64_MIN) returns 0x8000000000000000
```

## <a name="see-also"></a>Дополнительно

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[_cabs](cabs.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[imaxabs](imaxabs.md)
