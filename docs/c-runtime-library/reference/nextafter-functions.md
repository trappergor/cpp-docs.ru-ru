---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
ms.date: 04/05/2018
api_name:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
ms.openlocfilehash: c56c9f8032c9af2ed4404428abe3b9ee26b4b603
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951353"
---
# <a name="nextafter-nextafterf-nextafterl-_nextafter-_nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

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

Возвращает следующее представимое значение с плавающей запятой возвращаемого типа после *x* в направлении *y*. Если *x* и *y* равны, функция возвращает *y*, преобразованную в тип возвращаемого значения, без исключения. Если *x* не равно *y*, а результат имеет значение денормализованное или равное нулю, то задаются состояния исключения **FE_UNDERFLOW** и **FE_INEXACT** с плавающей запятой и возвращается правильный результат. Если либо *x* , либо *y* является NaN, то возвращаемое значение является одним из входных значений NaN. Если *x* является конечным, а результат является бесконечным или не может быть представлен в типе, возвращается правильно подписанная бесконечность или NaN, выдаются состояния исключения **FE_OVERFLOW** и **FE_INEXACT** с плавающей запятой **, а для** свойства "значение по ошибке" — **ERANGE** .

## <a name="remarks"></a>Примечания

Семейства функций **nextafter** и **нексттовард** эквивалентны, за исключением типа параметра *y*. Если *x* и *y* равны, возвращается значение *y* , преобразованное в тип возвращаемого значения.

Поскольку C++ допускает перегрузку, при включении \<cmath > можно вызывать перегрузки **nextafter** и **нексттовард** , возвращающие типы **float** и **Long** **Double** . В программе на языке C **nextafter** и **нексттовард** всегда возвращают **double**.

Функции **_nextafter** и **_nextafterf** относятся только к Майкрософт. Функция **_nextafterf** доступна только при компиляции для x64.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **некстафтерф**, **некстафтерл**, **_nextafterf**, **нексттовард**, **нексттовардф**, **нексттовардл**|\<math.h>|\<math.h> или \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> или \<cfloat>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
