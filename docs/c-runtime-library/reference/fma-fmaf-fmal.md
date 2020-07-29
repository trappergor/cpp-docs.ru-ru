---
title: fma, fmaf, fmal
ms.date: 4/2/2020
api_name:
- fma
- fmaf
- fmal
- _o_fma
- _o_fmaf
- _o_fmal
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: d82565ed53f311ef1b2cf5942d207bf96090bd13
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217003"
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

*&*<br/>
Второе значение для перемножения.

*гармошкой*<br/>
Значение для сложения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает `(x * y) + z`. Возвращаемое значение округляется с использованием текущего формата округления.

В случае неудачи может возвращать одно из следующих значений:

|Проблема|Возвращает|
|-----------|------------|
|*x* = бесконечность, *y* = 0 или<br /><br /> *x* = 0, *y* = бесконечность|Не число|
|*x* или *y* = точное ± бесконечности, *z* = бесконечность с противоположным знаком|Не число|
|*x* или *y* = NaN|Не число|
|not (*x* = 0, *y*= неопределенное) и *z* = NaN<br /><br /> not (*x*= неопределенный, *y*= 0) и *z* = NaN|Не число|
|Ошибка переполнения диапазона|± HUGE_VAL, ± HUGE_VALF или ± HUGE_VALL|
|Ошибка недостаточного заполнения диапазона|правильное значение (после округления).|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Remarks

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **FMA** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C **FMA** всегда принимает и возвращает **`double`** .

Эта функция вычисляет значение с бесконечной точностью, после чего округляет результат.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**FMA**, **фмаф**, **фмал**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
