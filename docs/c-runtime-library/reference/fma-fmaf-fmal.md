---
title: fma, fmaf, fmal
ms.date: 04/05/2018
api_name:
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
ms.openlocfilehash: 4ddc4061e5a24ee3b5176aedc569d134d85e0002
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957103"
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal

Перемножает два значения, добавляет к произведению третье значение и затем округляет результат без потери точности, вызванной промежуточным округлением.

## <a name="syntax"></a>Синтаксис

```C
double fma(
   double x,
   double y,
   double z
);

float fma(
   float  x,
   float  y,
   float z
); //C++ only

long double fma(
   long double  x,
   long double  y,
   long double z
); //C++ only

float fmaf(
   float  x,
   float  y,
   float z
);

long double fmal(
   long double  x,
   long double  y,
   long double z
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Первое значение для перемножения.

*y*<br/>
Второе значение для перемножения.

*z*<br/>
Значение для сложения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает `(x * y) + z`. Возвращаемое значение округляется с использованием текущего формата округления.

В случае неудачи может возвращать одно из следующих значений:

|Проблемы|Назад|
|-----------|------------|
|*x* = бесконечность, *y* = 0 или<br /><br /> *x* = 0, *y* = бесконечность|NaN|
|*x* или *y* = точное ± бесконечности, *z* = бесконечность с противоположным знаком|NaN|
|*x* или *y* = NaN|NaN|
|not (*x* = 0, *y*= неопределенное) и *z* = NaN<br /><br /> not (*x*= неопределенный, *y*= 0) и *z* = NaN|NaN|
|Ошибка переполнения диапазона|± HUGE_VAL, ± HUGE_VALF или ± HUGE_VALL|
|Ошибка недостаточного заполнения диапазона|правильное значение (после округления).|

Ошибки сообщаются, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **FMA** , которые принимают и возвращают типы **float** и **Long** **Double** . В программе на языке C **FMA** всегда принимает и возвращает значение **типа Double**.

Эта функция вычисляет значение с бесконечной точностью, после чего округляет результат.

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**FMA**, **фмаф**, **фмал**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
