---
title: acos, acosf, acosl
ms.date: 04/05/2018
api_name:
- acosf
- acos
- acosl
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
- acos
- acosl
- acosf
- math/acosf
- math/acosl
helpviewer_keywords:
- acos function
- acosl function
- acosf function
- trigonometric functions
- arccosine function
ms.assetid: 00b89c48-8faf-4824-aa95-fa4349a4975d
ms.openlocfilehash: 9e8aba1104af5855db9cb4f3cbb989d182b2c78e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939998"
---
# <a name="acos-acosf-acosl"></a>acos, acosf, acosl

Вычисляет арккосинус.

## <a name="syntax"></a>Синтаксис

```C
double acos( double x );
float acosf( float x );
long double acosl( long double x );
```

```cpp
float acos( float x );   // C++ only
long double acos( long double x );   // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение от-1 до 1, для которого вычисляется арккосинус (обратный косинус).

## <a name="return-value"></a>Возвращаемое значение

Функция **Acos** Возвращает арккосинус *x* в диапазоне от 0 до π радиан.

По умолчанию, если *x* меньше-1 или больше 1, **Acos** возвращает неопределенное значение.

|Ввод|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± ∞|INVALID|_DOMAIN|
|± КНАН, С|none|_DOMAIN|
|&#124;x&#124;>1|INVALID|_DOMAIN|

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **Acos** , которые принимают и возвращают типы **float** и **Long** **Double** . В программе на языке C **Acos** всегда принимает и возвращает значение **типа Double**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательные заголовки|
|-------------|---------------------|----------------------|
|**Acos**, **acosf**, **acosl**|\<math.h>|\<errno.h>|

## <a name="example"></a>Пример

Эта программа предлагает ввести значение в диапазоне от -1 до 1. Входные значения вне этого диапазона вызывают сообщения об ошибке `_DOMAIN`. Если введено допустимое значение, программа выводит на экран арксинус и арккосинус этого значения.

```C
// crt_asincos.c
// arguments: 0

#include <math.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( int ac, char* av[] )
{
    double  x,
            y;
    errno_t err;

    // argument checking
    if (ac != 2)
    {
        fprintf_s( stderr, "Usage: %s <number between -1 and 1>\n",
                   av[0]);
        return 1;
    }

    // Convert argument into a double value
    if ((err = sscanf_s( av[1], "%lf", &x )) != 1)
    {
        fprintf_s( stderr, "Error converting argument into ",
                   "double value.\n");
        return 1;
    }

    // Arcsine of X
    y = asin( x );
    printf_s( "Arcsine of %f = %f\n", x, y );

    // Arccosine of X
    y = acos( x );
    printf_s( "Arccosine of %f = %f\n", x, y );
}
```

```Output
Arcsine of 0.000000 = 0.000000
Arccosine of 0.000000 = 1.570796
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)