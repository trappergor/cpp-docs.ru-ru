---
title: atanh, atanhf, atanhl | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- atanhl
- atanhf
- atanh
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
- atanhl
- atanhf
- atanh
dev_langs:
- C++
helpviewer_keywords:
- atanhf function
- atanhl function
- atanh funciton
ms.assetid: 83a43b5b-2580-4461-854f-dc84236d9f32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90a24945a7d630fac909e097728ea4df61ae2b40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393307"
---
# <a name="atanh-atanhf-atanhl"></a>atanh, atanhf, atanhl

Вычисляет обратный гиперболический тангенс.

## <a name="syntax"></a>Синтаксис

```C
double atanh( double x );
float atanhf( float x );
long double atanhl( long double x );
```

```cpp
float atanh( float x );  // C++ only
long double atanh( long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

**Atanh** функции возвращают обратный гиперболический тангенс (гиперболический арктангенс) *x*. Если *x* больше 1 или меньше -1, **errno** равно **EDOM** и результатом является несигнальным значением NaN. Если *x* будет равно 1 или -1, положительная или отрицательная бесконечность возвращается, соответственно, и **errno** равно **ERANGE**.

|Входные данные|Исключение SEH|**Matherr** исключение|
|-----------|-------------------|-------------------------|
|± QNAN,IND|Нет|Нет|
|*X* ≥ 1; *x* ≤ -1|Нет|Нет|

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **atanh** , принимающие и возвращающие **float** или **длинные** **двойные** значения. В программе на языке C **atanh** всегда принимает и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**ATANH**, **atanhf**, **atanhl**|\<math.h>|\<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_atanh.c
// This program displays the hyperbolic tangent of pi / 4
// and the arc hyperbolic tangent of the result.
//

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = tanh( pi / 4 );
   y = atanh( x );
   printf( "tanh( %f ) = %f\n", pi/4, x );
   printf( "atanh( %f ) = %f\n", x, y );
}
```

```Output
tanh( 0.785398 ) = 0.655794
atanh( 0.655794 ) = 0.785398
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
