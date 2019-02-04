---
title: nearbyint, nearbyintf, nearbyintl
ms.date: 04/05/2018
apiname:
- nearbyint
- nearbyintf
- nearbyintl
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
ms.openlocfilehash: 827286c840c6564c8c3f8b351197b0201509d241
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703003"
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

В случае успешного выполнения возвращает *x*, округленное до ближайшего целого числа, с помощью текущего формата округления в соответствии с отчетом [fegetround](fegetround-fesetround2.md). В противном случае функция может вернуть одно из следующих значений:

|Проблемы|Назад|
|-----------|------------|
|*x* = ±INFINITY|±INFINITY, без изменений|
|*x* = ±0|±0, без изменений|
|*x* = NaN|NaN|

Ошибки не выводятся в [_matherr](matherr.md); в частности, эта функция не сообщает о любой **FE_INEXACT** исключения.

## <a name="remarks"></a>Примечания

Основное различие между этой функцией и [rint](rint-rintf-rintl.md) — это то, что эта функция не вызывает неточный точки исключения с плавающей запятой.

Так как максимальные значения с плавающей запятой являются точными целыми числами, эта функция никогда не будет переполняться сама по себе; вместо этого выходные данные могут привести к переполнению возвращаемого значения в зависимости от используемой функции.

C++ допускает перегрузку, поэтому можно вызывать перегрузки **nearbyint** , принимающие и возвращающие **float** или **long** **двойные** параметров. В программе на языке C **nearbyint** всегда принимает два значения типа double и возвращает значение типа double.

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**nearbyint**, **nearbyintf**, **nearbyintl**|\<math.h>|\<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[Математические и поддержка плавающей запятой](../floating-point-support.md)<br/>
