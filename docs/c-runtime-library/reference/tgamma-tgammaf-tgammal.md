---
title: tgamma, tgammaf, tgammal
description: Справочник по API для тгамма, tgammaf и тгаммал; , который определяет гамма-функцию указанного значения.
ms.date: 9/1/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b49020ca0697e920dccf188df4ad024820966571
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555180"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

Определяет гамма-функцию указанного значения.

## <a name="syntax"></a>Синтаксис

```C
double tgamma(
   double x
);

float tgammaf(
   float x
);

long double tgammal(
   long double x
);

#define tgamma(X) // Requires C11 or higher

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only
```

### <a name="parameters"></a>Параметры

*x*\
Значение, для которого требуется найти гамму.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает гамму *x*.

Ошибка диапазона может возникать, если величина *x* слишком велика или слишком мала для типа данных. Если *x* <= 0, может возникать ошибка домена или диапазона.

|Проблема|Возвращает|
|-----------|------------|
|x = ± 0|± Бесконечности|
|x = negative integer|NaN|
|x =-бесконечность|NaN|
|x = +INFINITY|+INFINITY|
|x = NaN|NaN|
|ошибка домена|NaN|
|Ошибка полюса|± HUGE_VAL, ± HUGE_VALF или ± HUGE_VALL|
|Ошибка переполнения диапазона|± HUGE_VAL, ± HUGE_VALF или ± HUGE_VALL|
|ошибка недостаточного заполнения диапазона|правильное значение (после округления).|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **тгамма** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **тгамма** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `tgamma()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

Если x является натуральным числом, эта функция возвращает факториал (x – 1).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**тгамма**, **tgammaf**,  **тгаммал**|\<math.h>|\<cmath>|
|макрос **тгамма** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
