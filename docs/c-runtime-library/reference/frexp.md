---
title: frexp, фрекспф, фрекспл
ms.date: 04/05/2018
api_name:
- frexp
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
- frexp
- _frexpl
helpviewer_keywords:
- _frexpl function
- mantissas, floating-point variables
- frexpl function
- exponent, floating-point numbers
- frexp function
- floating-point functions, mantissa and exponent
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
ms.openlocfilehash: 3a67ced9bd6653a7c40c98a8cf015663c37457bb
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956640"
---
# <a name="frexp-frexpf-frexpl"></a>frexp, фрекспф, фрекспл

Возвращает мантиссу и степень числа с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double frexp(
   double x,
   int *expptr
);
float frexpf(
   float x,
   int * expptr
);
long double frexpl(
   long double x,
   int * expptr
);
float frexp(
   float x,
   int * expptr
);  // C++ only
long double frexp(
   long double x,
   int * expptr
);  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

*експптр*<br/>
Указатель на сохраненное значение целой части числа.

## <a name="return-value"></a>Возвращаемое значение

**frexp** возвращает мантисса. Если *x* равно 0, функция возвращает 0 для мантиссаа и экспоненты. Если *експптр* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция **устанавливает** **еинвал** и возвращает 0.

## <a name="remarks"></a>Примечания

Функция **frexp** разбивает значение с плавающей запятой (*x*) в мантисса (*m*) и экспоненту (*n*) таким, что абсолютное значение *m* больше или равно 0,5 и меньше 1,0, и *x*  =  *m* * 2<sup>*n*</sup>. Целочисленная экспонента *n* хранится в расположении, на которое указывает *експптр*.

C++допускает перегрузку, поэтому можно вызывать перегрузки **frexp**. В программе на языке C **frexp** всегда принимает указатель типа **Double** и **int** и возвращает значение **типа Double**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**frexp**, **фрекспф**, **фрекспл**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_frexp.c
// This program calculates frexp( 16.4, &n )
// then displays y and n.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y;
   int n;

   x = 16.4;
   y = frexp( x, &n );
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );
}
```

```Output
frexp( 16.400000, &n ) = 0.512500, n = 5
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
