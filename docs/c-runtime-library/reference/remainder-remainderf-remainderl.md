---
title: remainder, remainderf, remainderl | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
dev_langs:
- C++
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52abbfef2e20bebd531ef2d6c7a414f8345d996b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

Вычисляет остаток от частного двух чисел с плавающей запятой, округленного до ближайшего целого значения.

## <a name="syntax"></a>Синтаксис

```C
double remainder( double x, double y );
float remainderf( float x, float y );
long double remainderl( long double x, long double y );
```

```cpp
float remainder( float x, float y ); /* C++ only */
long double remainder( long double x, long double y ); /* C++ only */
```

### <a name="parameters"></a>Параметры

*x*<br/>
Числитель.

*y*<br/>
Знаменатель.

## <a name="return-value"></a>Возвращаемое значение

Остаток с плавающей запятой из *x* / *y*. Если значение *y* равно 0,0, **остаток** возвращает несигнальным значением NaN. Сведения о представлении несигнальным значением NaN, **printf** семействах, см. в разделе [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Примечания

**Остаток** функции вычисляют остаток с плавающей запятой *r* из *x* / *y* таким образом, что *x*   =  *n* * *y* + *r*, где *n*— целое число, наиболее близкое к значению для *x* / *y* и *n*четное всякий раз, когда &#124; *n*  -  *x* / *y* &#124; = 1/2. Когда *r* = 0, *r* имеет тот же знак *x*.

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **остаток** , принимающие и возвращающие **float** или **длинные** **двойные** значения. В программе на языке C **остаток** всегда принимает два **двойные** аргументы и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|--------------|---------------------|-|
|**остаток**, **remainderf**, **remainderl**|\<math.h>|\<cmath> или \<math.h>|

Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_remainder.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = remainder(w, x);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
