---
title: erf, erff, erfl, erfc, erfcf, erfcl
ms.date: 4/2/2020
api_name:
- erff
- erfl
- erf
- erfc
- erfcf
- erfcl
- _o_erf
- _o_erfc
- _o_erfcf
- _o_erfcl
- _o_erff
- _o_erfl
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
- erfl
- erf
- erff
- erfc
- erfcf
- erfcl
helpviewer_keywords:
- erfl function
- erff function
- erf function
- erfcl function
- erfcf function
- erfc function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
ms.openlocfilehash: ad7ad279d3686e4f33a6f5f901c60348c131b89a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347925"
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl

Вычисляет функцию ошибок или дополнительную функцию ошибок значения.

## <a name="syntax"></a>Синтаксис

```C
double erf(
   double x
);
float erf(
   float x
); // C++ only
long double erf(
   long double x
); // C++ only
float erff(
   float x
);
long double erfl(
   long double x
);
double erfc(
   double x
);
float erfc(
   float x
); // C++ only
long double erfc(
   long double x
); // C++ only
float erfcf(
   float x
);
long double erfcl(
   long double x
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **erf** возвращают функцию ошибки Гаусса *x.* Функции **erfc** возвращают функцию ошибки Гаусса *x*.

## <a name="remarks"></a>Remarks

Функции **erf** вычисляют функцию ошибки Gauss *x,* которая определена как:

![Функцию ошибок от x](media/crt_erf_formula.PNG "Функцию ошибок от x")

Дополнительная функция ошибки Гаусса определяется как 1 - erf(x). Функции **erf** возвращают значение в диапазоне от -1.0 до 1.0. Ошибка не возвращается. Функции **erfc** возвращают значение в диапазоне от 0 до 2. Если *x* слишком велик для **erfc,** переменная **errno** установлена на **ERANGE.**

Из-за того, что СЗ позволяет перегружать, можно вызывать перегрузки **erf** и **erfc,** которые принимают и возвращают **плавающие** и **длинные** **двойные** типы. В программе C, **erf** и **erfc** всегда принимают и возвращают **двойник.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**erf**, **erff**, **erfl**, **erfc**, **erfcf**, **erfcl**|\<math.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
