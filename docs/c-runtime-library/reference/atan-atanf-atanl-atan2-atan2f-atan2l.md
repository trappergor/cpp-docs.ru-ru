---
title: atan, atanf, atanl, atan2, atan2f, atan2l
description: Справочник по API для Atan, атанф, атанл, atan2, atan2f и atan2l; который Вычисляет арктангенс значения с плавающей запятой.
ms.date: 08/31/2020
api_name:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
- _o_atan
- _o_atan2
- _o_atan2f
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
- atan
- atan2l
- atan2
- atanl
- atanf
- atan2f
helpviewer_keywords:
- atan function
- atanf function
- atanl function
- atan2 function
- atan2l function
- arctangent function
- trigonometric functions
- atan2f function
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
ms.openlocfilehash: 1f1d33aac86d94ab3731dd5cf5b124af99ccb3f2
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555635"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan, atanf, atanl, atan2, atan2f, atan2l

Вычисляет арктангенс значений **x** (**ATAN**, **атанф**и **атанл**) или арктангенс **y** / **x** (**atan2**, **atan2f**и **atan2l**).

## <a name="syntax"></a>Синтаксис

```C
double atan( double x );
float atanf( float x );
long double atanl( long double x );
#define atan(X) // Requires C11 or higher

float atan( float x );  // C++ only
long double atan( long double x );  // C++ only

double atan2( double y, double x );
float atan2f( float y, float x );
long double atan2l( long double y, long double x );
#define atan2(Y, X) // Requires C11 or higher

float atan2( float y, float x );  // C++ only
long double atan2( long double y, long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*, *y*\
Все числа.

## <a name="return-value"></a>Возвращаемое значение

**ATAN** возвращает арктангенс *x* в диапазоне от-π/2 до π/2 радиан. **atan2** возвращает арктангенс *оси y* / *x* в диапазоне от-π до π радиан. Если *x* равно 0, **ATAN** возвращает 0. Если оба параметра **atan2** равны 0, функция возвращает 0. Все результаты даются в радианах.

**atan2** использует символы обоих параметров для определения квадранта возвращаемого значения.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± **КНАН**, **с**|нет|**_DOMAIN**|

## <a name="remarks"></a>Примечания

Функция **ATAN** Вычисляет арктангенс (обратную функцию тангенса) для *x*. **atan2** Вычисляет арктангенс *y* / *x* (если *x* равен 0, **atan2** возвращает π/2, если *y* является положительным,-π/2, если *y* является отрицательным, или 0, если *y* равен 0).

При использовании \<tgmath.h> `atan()` `atan2()` макроса или тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

**ATAN** имеет реализацию, использующую Streaming SIMD Extensions 2 (SSE2). Сведения о реализации SSE2 и ограничениях на ее использование см. в разделе [_set_SSE2_enable](set-sse2-enable.md).

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **ATAN** и **atan2** , которые принимают **`float`** **`long double`** аргументы или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **ATAN** и **atan2** всегда принимают **`double`** аргументы и возвращают **`double`** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------|-|
|**ATAN**, **atan2**, **атанф**, **atan2f**, **атанл**, **atan2l**|\<math.h>|\<cmath> или \<math.h>|
|**ATAN ()**, макросы **atan2** | \<tgmath.h> ||

## <a name="example"></a>Пример

```C
// crt_atan.c
// arguments: 5 0.5
#include <math.h>
#include <stdio.h>
#include <errno.h>

int main( int ac, char* av[] )
{
   double x, y, theta;
   if( ac != 3 ){
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );
      return 1;
   }
   x = atof( av[1] );
   theta = atan( x );
   printf( "Arctangent of %f: %f\n", x, theta );
   y = atof( av[2] );
   theta = atan2( y, x );
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );
   return 0;
}
```

```Output
Arctangent of 5.000000: 1.373401
Arctangent of 0.500000 / 5.000000: 0.099669
```

## <a name="see-also"></a>См. также

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIatan](../../c-runtime-library/ciatan.md)<br/>
[_CIatan2](../../c-runtime-library/ciatan2.md)<br/>
