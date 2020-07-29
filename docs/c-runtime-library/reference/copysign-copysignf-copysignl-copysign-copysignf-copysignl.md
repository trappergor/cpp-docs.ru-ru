---
title: copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl
ms.date: 04/05/2018
api_name:
- copysignf
- copysignl
- _copysignl
- _copysign
- _copysignf
- copysign
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
- _copysignl
- copysign
- copysignf
- _copysign
- copysignl
- _copysignf
helpviewer_keywords:
- copysignl function
- _copysignl function
- copysign function
- _copysignf function
- _copysign function
- copysignf function
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
ms.openlocfilehash: 4dea95240dcbd3dbbf221ff7af80a9e3ee554e23
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221943"
---
# <a name="copysign-copysignf-copysignl-_copysign-_copysignf-_copysignl"></a>copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl

Возвращает значение, которое имеет абсолютное значение одного аргумента и знак другого.

## <a name="syntax"></a>Синтаксис

```C
double copysign(
   double x,
   double y
);
float copysign(
   float x,
   float y
); // C++ only
long double copysign(
   long double x,
   long double y
); // C++ only
float copysignf(
   float x,
   float y
); // C++ only
long double copysignl(
   long double x,
   long double y
); // C++ only
double _copysign(
   double x,
   double y
);
long double _copysignl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой, которое возвращается как абсолютное значение результата.

*&*<br/>
Значение с плавающей запятой, которое возвращается как знак результата.

[Подпрограммы поддержки чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)

## <a name="return-value"></a>Возвращаемое значение

Функции **кописигн** возвращают значение с плавающей запятой, объединяющее величину *x* и знак *y*. Ошибка не возвращается.

## <a name="remarks"></a>Remarks

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **кописигн** , которые принимают и возвращают **`float`** **`long double`** значения или. В программе на языке C **кописигн** всегда принимает и возвращает **`double`** .

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_copysign**|\<float.h>|
|**кописигн**, **кописигнф**, **кописигнл**, **_copysignf**, **_copysignl**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[_chgsign, _chgsignf, _chgsignl](chgsign-chgsignf-chgsignl.md)<br/>
