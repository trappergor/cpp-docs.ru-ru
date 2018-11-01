---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
ms.date: 04/05/2018
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
ms.openlocfilehash: 0e0a60dc9f7c068d8c18c10f3c6b819b9e06d3b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444868"
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

Возвращает следующее представимое значение с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );
```

```cpp
float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>Параметры

*x*<br/>
Начальное значение с плавающей запятой.

*y*<br/>
Следующее значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Возвращает следующее представимое значение с плавающей запятой возвращаемого типа после *x* в направлении *y*. Если *x* и *y* равны, функция возвращает *y*, преобразованное в возвращаемый тип, с помощью исключение не запускается. Если *x* не равно *y*, а результатом является денормализованное число или нуль, **FE_UNDERFLOW** и **FE_INEXACT** состояний исключения с плавающей запятой заданы, и возвращается правильный результат. Если параметр *x* или *y* имеет значение NAN, то возвращаемое значение является одним из входных значений NaN. Если *x* является конечным и результат является бесконечным или не может быть представлен в типе, бесконечность со знаком возвращается значение NAN или, **FE_OVERFLOW** и **FE_INEXACT** задаются состояния исключения с плавающей запятой, и **errno** присваивается **ERANGE**.

## <a name="remarks"></a>Примечания

**Nextafter** и **nexttoward** семейства функций эквивалентны за исключением типа параметра *y*. Если *x* и *y* равны, возвращается значение *y* преобразуется в тип возвращаемого значения.

Поскольку C++ допускает перегрузку, если включить \<cmath > можно вызывать перегрузки **nextafter** и **nexttoward** , которые возвращают **float** и **long** **двойные** типов. В программе на языке C **nextafter** и **nexttoward** всегда возвращать **двойные**.

**_Nextafter** и **_nextafterf** функции только к системам Майкрософт. **_Nextafterf** функция доступна только в том случае, при компиляции для x64.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nexttoward**, **nexttowardf** , **nexttowardl**|\<math.h>|\<math.h> или \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> или \<cfloat>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
