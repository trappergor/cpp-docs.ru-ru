---
title: erf, erff, erfl, erfc, erfcf, erfcl
description: Справочник по API для Фош, erff, ерфл, ерфк, ерфкф и ерфкл; который рассчитывает функцию ошибки или дополнительную функцию ошибки значения.
ms.date: 9/1/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: ef83275515c66341798395bbfc2bb5b088e6cfb7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555648"
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
#define erf(X) // Requires C11 or higher
#define erfc(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **Фош** возвращают функцию Гаусса Error типа *x*. Функции **ерфк** возвращают дополняющую функцию ошибки Гаусса *x*.

## <a name="remarks"></a>Примечания

Функции **Фош** вычисляют функцию Гаусса Error *x*, которая определяется следующим образом:

![Функцию ошибок от x](media/crt_erf_formula.PNG "Функцию ошибок от x")

Функция дополнения Гаусса Error определяется как 1-Фош (x). Функции **Фош** возвращают значение в диапазоне от-1,0 до 1,0. Ошибки не возвращаются. Функции **ерфк** возвращают значение в диапазоне от 0 до 2. Если *x* слишком велико для **ерфк**, то для переменной « **No** » задано значение **ERANGE**.

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **Фош** и **ерфк** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **Фош** и **ерфк** всегда принимают и возвращают **`double`** .

При использовании \<tgmath.h> `erf()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**Фош**, **erff**, **ерфл**, **ерфк**, **ерфкф**, **ерфкл**|\<math.h>|
|**Фош** , макрос | \<tgmath.h> |

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
