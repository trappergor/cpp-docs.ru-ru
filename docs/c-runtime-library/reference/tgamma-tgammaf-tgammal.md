---
title: tgamma, tgammaf, tgammal
ms.date: 4/2/2020
api_name:
- tgamma
- tgammaf
- tgammal
- _o_tgamma
- _o_tgammaf
- _o_tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
ms.openlocfilehash: d7e27e8b818a16cb0c18f58e2f40c0090dd13ecf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362508"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

Определяет гамма-функцию указанного значения.

## <a name="syntax"></a>Синтаксис

```C
double tgamma(
   double x
);

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only

float tgammaf(
   float x
);

long double tgammal(
   long double x
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение, для которого требуется найти гамму.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха, возвращает гамму *х*.

Ошибка диапазона может произойти, если величина *x* слишком велика или слишком мала для типа данных. Ошибка домена или ошибка диапазона может произойти, если *x* <и 0.

|Проблемы|Возвращает|
|-----------|------------|
|х 0 евро|(ИНФИНИТИЯ)|
|x = negative integer|NaN|
|х -ИНФИНИОНГИ|NaN|
|x = +INFINITY|+INFINITY|
|x = NaN|NaN|
|ошибка домена|NaN|
|Ошибка полюса|HUGE_VAL, HUGE_VALF или HUGE_VALL|
|Ошибка переполнения диапазона|HUGE_VAL, HUGE_VALF или HUGE_VALL|
|ошибка недостаточного заполнения диапазона|правильное значение (после округления).|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Remarks

Из-за того, что СЗ позволяет перегружать, можно вызывать перегрузки **тгаммы,** которые принимают и возвращают **плавающие** и **длинные** **двойные** типы. В программе **C, tgamma** всегда принимает и возвращает **двойник.**

Если x является натуральным числом, эта функция возвращает факториал (x – 1).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**tgamma**, **tgammaf**, **tgammal**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
