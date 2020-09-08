---
title: fma, fmaf, fmal
description: Справочник по API для FMA, фмаф и фмал; который умножает два значения, добавляет третье значение, а затем округляет результат без потери точности из-за промежуточного округления.
ms.date: 9/1/2020
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
ms.openlocfilehash: e9ae92c28f24b6281d73450c7cabaad775a84d42
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556701"
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal

Умножает два значения вместе, добавляет третье значение, а затем округляет результат без потери точности из-за промежуточного округления.

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

#define fma(X, Y, Z) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Первое значение для перемножения.

*&*\
Второе значение для перемножения.

*гармошкой*\
Значение для сложения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает `(x * y) + z`. Возвращаемое значение округляется с использованием текущего формата округления.

В случае неудачи может возвращать одно из следующих значений:

|Проблема|Возвращает|
|-----------|------------|
|*x* = бесконечность, *y* = 0 или<br /><br /> *x* = 0, *y* = бесконечность|NaN|
|*x* или *y* = точное ± бесконечности, *z* = бесконечность с противоположным знаком|NaN|
|*x* или *y* = NaN|NaN|
|not (*x* = 0, *y*= неопределенное) и *z* = NaN<br /><br /> not (*x*= неопределенный, *y*= 0) и *z* = NaN|NaN|
|Ошибка переполнения диапазона|± HUGE_VAL, ± HUGE_VALF или ± HUGE_VALL|
|Ошибка недостаточного заполнения диапазона|правильное значение (после округления).|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **FMA** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **FMA** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `fma()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

Эта функция вычисляет значение с бесконечной точностью, после чего округляет результат.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**FMA**, **фмаф**, **фмал**|\<math.h>|\<cmath>|
|макрос **FMA** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
