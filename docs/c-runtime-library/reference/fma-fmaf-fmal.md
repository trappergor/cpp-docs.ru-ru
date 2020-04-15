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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 993ca4d57202b3789929161a964b3e41d48fd98f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346571"
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

*Y*<br/>
Второе значение для перемножения.

*Z*<br/>
Значение для сложения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает `(x * y) + z`. Возвращаемое значение округляется с использованием текущего формата округления.

В случае неудачи может возвращать одно из следующих значений:

|Проблемы|Возвращает|
|-----------|------------|
|*х* - ИНФИНИТИОН, *у* й 0 или<br /><br /> *х* 0, *у-инфинитизм*|NaN|
|*x* или *y* - точная - ИНФИНИТИЯ, *z* - INFINITY с противоположным знаком|NaN|
|*x* или *y* - NaN|NaN|
|нет *(х* 0, *у*неопределенный срок) и *z*<br /><br /> нет *(х*неопределенный, *у*Й0) и *z*|NaN|
|Ошибка переполнения диапазона|HUGE_VAL, HUGE_VALF или HUGE_VALL|
|Ошибка недостаточного заполнения диапазона|правильное значение (после округления).|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Remarks

Из-за того, что СЗ позволяет перегружать, можно вызывать перегрузки **FMA,** которые принимают и возвращают **поплавок,** и **длинные** **двойные** типы. В программе C, **fma** всегда принимает и возвращает **двойник.**

Эта функция вычисляет значение с бесконечной точностью, после чего округляет результат.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**fma**, **fmaf**, **fmal**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
