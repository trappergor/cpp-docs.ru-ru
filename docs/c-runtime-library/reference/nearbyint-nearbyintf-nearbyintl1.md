---
title: nearbyint, nearbyintf, nearbyintl
ms.date: 04/05/2018
api_name:
- nearbyint
- nearbyintf
- nearbyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
ms.openlocfilehash: cd0a7d00c5019dd1e483d555df6db8d9770e61c1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951393"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

Округляет заданное значение с плавающей запятой до целого числа и возвращает это значение в формате с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
```

```cpp
float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение для округления.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает значение *x*, округленное до ближайшего целого числа, используя текущий формат округления, сообщаемый [fegetround](fegetround-fesetround2.md). В противном случае функция может вернуть одно из следующих значений:

|Проблемы|Назад|
|-----------|------------|
|*x* = ± бесконечности|± Бесконечности, без изменений|
|*x* = ± 0|± 0, без изменений|
|*x* = NaN|NaN|

Сообщения об ошибках не передаются через [_matherr](matherr.md); в частности, эта функция не сообщает об исключениях **FE_INEXACT** .

## <a name="remarks"></a>Примечания

Основное различие между этой функцией и [Печать](rint-rintf-rintl.md) заключается в том, что эта функция не вызывает неточного исключения с плавающей точкой.

Так как максимальные значения с плавающей запятой являются точными целыми числами, эта функция никогда не будет переполняться сама по себе; вместо этого выходные данные могут привести к переполнению возвращаемого значения в зависимости от используемой функции.

C++допускает перегрузку, поэтому можно вызывать перегрузки **неарбинт** , которые принимают и возвращают параметры с **плавающей запятой** или **длинные** **Double** . В программе на языке C **неарбинт** всегда принимает два значения типа Double и возвращает значение типа Double.

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**неарбинт**, **неарбинтф**, **неарбинтл**|\<math.h>|\<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[Поддержка математических функций и чисел с плавающей запятой](../floating-point-support.md)<br/>
