---
title: fmod, fmodf, fmodl | Документы Microsoft
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fmod
- fmodf
- fmodl
apilocation:
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
apitype: DLLExport
f1_keywords:
- fmod
- _fmodl
- fmodf
dev_langs:
- C++
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmodl function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f6cc8cc10c026c5ecd621657c556da883c187f5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fmod-fmodf-fmodl"></a>fmod, fmodf, fmodl

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

**fmod** возвращает остаток с плавающей запятой *x* / *y*. Если значение *y* равно 0,0, **fmod** возвращает несигнальным значением NaN. Сведения о представлении несигнальным значением NaN, **printf** семействах, см. в разделе [printf](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Примечания

**Fmod** функция вычисляет остаток с плавающей запятой *f* из *x* / *y* таким образом, что *x*  =  *я* * *y* + *f*, где *я* является целым числом, *f* имеет тот же знак *x*и абсолютное значение *f* меньше, чем абсолютное значение *y*.

C++ допускает перегрузки, поэтому можно вызывать перегрузки **fmod** , принимающие и возвращающие **float** и **длинные** **двойные** значения. В программе на языке C **fmod** всегда принимает два **двойные** аргументы и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fmod**, **fmodf**, **fmodl**|\<math.h>|

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
