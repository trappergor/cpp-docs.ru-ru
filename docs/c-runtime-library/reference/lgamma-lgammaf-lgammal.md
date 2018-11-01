---
title: lgamma, lgammaf, lgammal
ms.date: 04/05/2018
apiname:
- lgamma
- lgammaf
- lgammal
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
ms.openlocfilehash: 43ce1599ab9161b9fadf5643ddd2ec739ab2d8b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533488"
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

В случае успешного выполнения возвращает натуральный логарифм абсолютного значения гамма-функции для *x*.

|Проблемы|Назад|
|-----------|------------|
|*x* = NaN|NaN|
|*x* = ±0|+INFINITY|
|*x*= отрицательное целое число|+INFINITY|
|±INFINITY|+INFINITY|
|ошибка полюса|+HUGE_VAL, +HUGE_VALF или +HUGE_VALL|
|Ошибка переполнения диапазона|±HUGE_VAL, ±HUGE_VALF или ±HUGE_VALL|

Ошибки сообщаются, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Так как C++ допускает перегрузку, можно вызывать перегрузки **lgamma** , принимающие и возвращающие **float** и **long** **двойные** типов. В программе на языке C **lgamma** всегда принимает и возвращает **двойные**.

Если x является рациональным числом, эта функция возвращает логарифм факториала (x - 1).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**lgamma**, **lgammaf**, **lgammal**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
