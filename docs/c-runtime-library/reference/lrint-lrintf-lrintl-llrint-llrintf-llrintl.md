---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl
description: Справочник по API для лринт (), лринтф (), лринтл (), ллринт (), ллринтф () и ллринтл (); что Округляет указанное значение с плавающей запятой до ближайшего целого значения, используя текущий режим округления и направление.
ms.date: 9/1/2020
api_name:
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
- _o_llrint
- _o_llrintf
- _o_llrintl
- _o_lrint
- _o_lrintf
- _o_lrintl
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
- lrint
- lrintf
- lrintl
- llrint
- llrintf
- llrintl
- math/lrint
- math/lrintf
- math/lrintl
- math/llrint
- math/llrintf
- math/llrintl
helpviewer_keywords:
- lrint function
- lrintf function
- lrintl function
- llrint function
- llrintf function
- llrintl function
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
ms.openlocfilehash: f208c183400aac7a110bb6fd87398d4377fe8f06
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555024"
---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint, lrintf, lrintl, llrint, llrintf, llrintl

Округляет указанное значение с плавающей запятой до ближайшего целого значения, используя текущие режим и направление округления.

## <a name="syntax"></a>Синтаксис

```C
long int lrint(
   double x
);

long int lrint(
   float x
); //C++ only

long int lrint(
   long double x
); //C++ only

long int lrintf(
   float x
);

long int lrintl(
   long double x
);

long long int llrint(
   double x
);

long long int llrint(
   float x
); //C++ only

long long int llrint(
   long double x
); //C++ only

long long int llrintf(
   float x
);

long long int llrintl(
   long double x
);

#define lrint(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Значение для округления.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает округленное целочисленное значение *x*.

|Проблема|Возвращает|
|-----------|------------|
|*x* находится за пределами диапазона возвращаемого типа<br /><br /> *x* = ± ∞<br /><br /> *x* = NaN|Вызывает **FE_INVALID** и возвращает ноль (0).|

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **лринт** и **ллринт** , которые принимают **`float`** **`long double`** типы и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **лринт** и **ллринт** всегда принимают **`double`** .

При использовании \<tgmath.h> `llrint()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

Если *x* не представляет эквивалент целочисленного значения с плавающей запятой, эти функции вызывают **FE_INEXACT**.

**Конкретно для Майкрософт**: Если результат находится вне диапазона возвращаемого типа или если параметр является NaN или бесконечностью, то возвращаемое значение определяется реализацией. Компилятор Майкрософт возвращает нулевое значение (0).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**лринт**, **лринтф**, **лринтл**, **ллринт**, **ллринтф**, **ллринтл**|\<math.h>|\<cmath>|
|макрос **лринт** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)
