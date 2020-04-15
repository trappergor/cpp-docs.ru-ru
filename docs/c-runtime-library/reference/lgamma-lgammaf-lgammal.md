---
title: lgamma, lgammaf, lgammal
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: e2bdfbeac7b995be0b589156437a3ded39114adf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342164"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

Определяет натуральный логарифм абсолютного значения гамма-функции для указанного значения.

## <a name="syntax"></a>Синтаксис

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Вычисляемое значение.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха, вернуть естественный logarithm абсолютное значение гамма-функции *х*.

|Проблемы|Возвращает|
|-----------|------------|
|*х* - NaN|NaN|
|*х* 0 евро|+INFINITY|
|*х*- отрицательный ателье|+INFINITY|
|(ИНФИНИТИЯ)|+INFINITY|
|Ошибка полюса|+HUGE_VAL, +HUGE_VALF или +HUGE_VALL|
|Ошибка переполнения диапазона|HUGE_VAL, HUGE_VALF или HUGE_VALL|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Remarks

Из-за того, что СЗ позволяет перегружать, можно вызывать перегрузки **lgamma,** которые принимают и возвращают **поплавок,** и **длинные** **двойные** типы. В программе C, **lgamma** всегда берет и возвращает **двойной**.

Если x является рациональным числом, эта функция возвращает logarithm факториального (x - 1).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**lgamma**, **lgammaf**, **lgammal**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
