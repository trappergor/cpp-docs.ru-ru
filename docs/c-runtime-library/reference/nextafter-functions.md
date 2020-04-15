---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
ms.date: 4/2/2020
api_name:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
- _o__nextafter
- _o_nextafter
- _o_nextafterf
- _o_nextafterl
- _o_nexttoward
- _o_nexttowardf
- _o_nexttowardl
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 7b1416147ed000dd3dd9a13bd52e41a474a8e9d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338568"
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

*Y*<br/>
Следующее значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Возвращает следующее представленное значение плавающей точки типа возврата после *x* в направлении *y.* Если *x* и *y* равны, функция *возвращаетy*, преобразованная в тип возврата, без исключения срабатывает. Если *x* не равен *y,* и результат денормальный или нулевой, **FE_UNDERFLOW** и **FE_INEXACT** состояния х-то исключением установлены, и правильный результат возвращается. Если *x* или *y* является NAN, то значение возврата является одним из входных NANs. Если *x* конечно и результат бесконечен или не представлен в типе, возвращается правильно подписанная бесконечность или NAN, FE_OVERFLOW **и** **FE_INEXACT** состояния исключения плавающей точки установлены, и **errno** настроенна на **ERANGE.**

## <a name="remarks"></a>Remarks

Далее и **nextafter** и **nexttoward** функции семейства эквивалентны, за исключением типа параметра *y*. Если *x* и *y* равны, возвратное значение *преобразуется в* тип возврата.

Поскольку СЗ допускает \<перегрузку, если включить cmath> вы можете вызвать перегрузки **nextafter** и **nexttoward,** которые **возвращаются поплавок** и **длинные** **двойные** типы. В программе C, **nextafter** и **nexttoward** всегда возвращаются **двойным**.

**Функции _nextafter** и **_nextafterf** специфичны для майкрософт. Функция **_nextafterf** доступна только при компиляции для x64.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------------|-------------------------------|
|**Nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nexttoward**, **nexttowardf**, **nexttowardl**|\<math.h>|\<math.h> или \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> или \<cfloat>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
