---
title: lgamma, lgammaf, lgammal
description: Справочник по API для лгамма, лгаммаф и лгаммал; , который определяет натуральный логарифм абсолютного значения гамма-функции указанного значения.
ms.date: 9/1/2020
api_name:
- lgamma
- lgammaf
- lgammal
- _o_lgamma
- _o_lgammaf
- _o_lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: 202250f3575f61fcef1cf29a687b8fdf36e6db33
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555401"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

Определяет натуральный логарифм абсолютного значения гамма-функции для указанного значения.

## <a name="syntax"></a>Синтаксис

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
#define lgammal(X) // Requires C11 or higher

float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>Параметры

*x*\
Вычисляемое значение.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает натуральный логарифм абсолютного значения гамма-функции *x*.

|Проблема|Возвращает|
|-----------|------------|
|*x* = NaN|NaN|
|*x* = ± 0|+INFINITY|
|*x*= отрицательное целое число|+INFINITY|
|± Бесконечности|+INFINITY|
|Ошибка полюса|+HUGE_VAL, +HUGE_VALF или +HUGE_VALL|
|Ошибка переполнения диапазона|± HUGE_VAL, ± HUGE_VALF или ± HUGE_VALL|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **лгамма** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **лгамма** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `lgamma()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

Если x является рациональным числом, эта функция возвращает логарифм факториала (x-1).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**лгамма**, **лгаммаф**, **лгаммал**|\<math.h>|\<cmath>|
|макрос **лгамма** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
