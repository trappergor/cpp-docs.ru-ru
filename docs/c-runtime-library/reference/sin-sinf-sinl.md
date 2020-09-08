---
title: sin, sinf, sinl
description: Справочник по API для SIN, sinf и sinl; , который вычисляет синус значения с плавающей запятой.
ms.date: 08/31/2020
api_name:
- sinl
- sinf
- sin
- _o_sin
- _o_sinf
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _sinl
- sinf
- sinl
- sin
helpviewer_keywords:
- _sinl function
- sinl function
- calculating sines
- sin function
- trigonometric functions
- sinf function
ms.assetid: 737de73e-3590-45f9-8257-dc1c0c489dfc
ms.openlocfilehash: 7d1921dd4537c9dcc955c264a36992d86defada8
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556196"
---
# <a name="sin-sinf-sinl"></a>sin, sinf, sinl

Вычисляет синус значения с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double sin(double x);
float sinf(float x);
long double sinl(long double x);
#define sin(x) // Requires C11 or higher
```

```cpp
float sin(float x);  // C++ only
long double sin(long double x);  // C++ only
```

### <a name="parameters"></a>Параметры

*x*\
Угол в радианах.

## <a name="return-value"></a>Возвращаемое значение

Функции **sin** возвращают синус *x*. Если значение *x* больше или равно 263 или меньше или равно-263, то происходит отрицательное значение в результате.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± КНАН, С|Нет|_DOMAIN|
|± ∞ (SIN, sinf, sinl)|INVALID|_DOMAIN|

Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **sin** , которые принимают и возвращают **`float`** **`long double`** значения или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, функция **sin** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `sin()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-|-|-|
|**sin**, **sinf**, **sinl**|\<math.h>|\<cmath> или \<math.h>|
|макрос **sin ()** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_sincos.c
// This program displays the sine and cosine of pi / 2.
// Compile by using: cl /W4 crt_sincos.c

#include <math.h>
#include <stdio.h>

int main( void)
{
   double pi = 3.1415926535;
   double x, y;

   x = pi / 2;
   y = sin( x );
   printf( "sin( %f ) = %f\n", x, y );
   y = cos( x );
   printf( "cos( %f ) = %f\n", x, y );
}
```

```Output
sin( 1.570796 ) = 1.000000
cos( 1.570796 ) = 0.000000
```

## <a name="see-also"></a>См. также

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIsin](../../c-runtime-library/cisin.md)<br/>
