---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c68d039ff1318ea082d409078a55c8d337a48de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403720"
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

Возвращает следующий представимым значением с плавающей запятой типа возвращаемого значения после *x* в направлении *y*. Если *x* и *y* равны, функция возвращает *y*, преобразованным в тип возврата с исключений не запускается. Если *x* не равно *y*, и результатом является denormal, либо ноль **FE_UNDERFLOW** и **FE_INEXACT** состояний исключений с плавающей запятой заданы, и возвращается правильный результат. Если параметр *x* или *y* является NAN, то возвращаемое значение является одним из входных значений NaN. Если *x* имеет конечные размеры и результатом является бесконечной или не может быть представлен в типе, правильно подписанного infinity или NAN возвращается, **FE_OVERFLOW** и **FE_INEXACT** заданы состояний исключений с плавающей запятой, и **errno** равно **ERANGE**.

## <a name="remarks"></a>Примечания

**Nextafter** и **nexttoward** функции семейства эквивалентны, за исключением типа параметра *y*. Если *x* и *y* равны, возвращается значение *y* преобразованы в тип возвращаемого значения.

Поскольку C++ допускает перегрузки, при включении \<cmath > можно вызывать перегрузки **nextafter** и **nexttoward** , возвращающее **float** и **long** **двойные** типов. В программе на языке C **nextafter** и **nexttoward** всегда возвращают **двойные**.

**_Nextafter** и **_nextafterf** функции — только к системам Майкрософт. **_Nextafterf** функция доступна только при компиляции для x64.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nexttoward**, **nexttowardf** , **nexttowardl**|\<math.h>|\<math.h> или \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> или \<cfloat>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
