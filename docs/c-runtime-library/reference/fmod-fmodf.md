---
title: FMOD, фмодф, фмодл
ms.date: 04/05/2018
api_name:
- fmod
- fmodf
- fmodl
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fmod
- _fmodl
- fmodf
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmodl function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
ms.openlocfilehash: e98432a73df8b872593d4cd610139bdfa72a25c4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957079"
---
# <a name="fmod-fmodf-fmodl"></a>FMOD, фмодф, фмодл

Вычисляет остаток с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double fmod(
   double x,
   double y
);
float fmod(
   float x,
   float y
);  // C++ only
long double fmod(
   long double x,
   long double y
);  // C++ only
float fmodf(
   float x,
   float y
);
long double fmodl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Параметры

*x*, *y*<br/>
Значения с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

**FMOD** возвращает остаток от деления *x* / *y*на значение с плавающей запятой. Если значение *y* равно 0,0, **FMOD** возвращает нетихом NaN. Сведения о представлении нескрытого числа NaN в семействе **printf** см. в разделе [printf](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Примечания

Функция **FMOD** вычисляет значение *x* / *y* *остатка* с плавающей запятой, т. е *. x* = *i* \* *y* + *f*, где *i* — целое число, *f* имеет тот же знак, что и *x*, а абсолютное значение *f* меньше, чем абсолютное значение *y*.

C++допускает перегрузку, поэтому можно вызывать перегрузки **FMOD** , которые принимают и возвращают значения **float** и **Long** **Double** . В программе на языке C **FMOD** всегда принимает два аргумента **Double** и возвращает значение **типа double**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**FMOD**, **фмодф**, **фмодл**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fmod.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = fmod( w, x );
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[_CIfmod](../../c-runtime-library/cifmod.md)<br/>
