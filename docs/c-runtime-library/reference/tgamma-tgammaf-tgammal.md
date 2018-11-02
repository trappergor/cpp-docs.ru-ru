---
title: tgamma, tgammaf, tgammal
ms.date: 04/05/2018
apiname:
- tgamma
- tgammaf
- tgammal
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
ms.openlocfilehash: 6cfe455b0e9e83cd5283d36fed33ca168bc97d0a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570668"
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

В случае успешного выполнения возвращает гамму *x*.

Ошибка диапазона может возникнуть, если абсолютное значение *x* слишком велико или слишком мал для типа данных. Ошибка домена или Ошибка диапазона может возникнуть, если *x* < = 0.

|Проблемы|Назад|
|-----------|------------|
|x = ±0|±INFINITY|
|x = negative integer|NaN|
|x = - INFINITY|NaN|
|x = +INFINITY|+INFINITY|
|x = NaN|NaN|
|ошибка домена|NaN|
|ошибка полюса|±HUGE_VAL, ±HUGE_VALF или ±HUGE_VALL|
|ошибка переполнения диапазона|±HUGE_VAL, ±HUGE_VALF или ±HUGE_VALL|
|ошибка недостаточного заполнения диапазона|правильное значение (после округления).|

Ошибки сообщаются, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Так как C++ допускает перегрузку, можно вызывать перегрузки **tgamma** , принимающие и возвращающие **float** и **long** **двойные** типов. В программе на языке C **tgamma** всегда принимает и возвращает **двойные**.

Если x является натуральным числом, эта функция возвращает факториал (x – 1).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**tgamma**, **tgammaf**, **tgammal**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
