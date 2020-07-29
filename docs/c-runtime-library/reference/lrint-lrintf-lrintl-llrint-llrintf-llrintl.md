---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl
ms.date: 4/2/2020
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
ms.openlocfilehash: c692b97598e2342628c3171fc22aeead9c864d60
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216912"
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
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение для округления.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает округленное целочисленное значение *x*.

|Проблема|Возвращает|
|-----------|------------|
|*x* находится за пределами диапазона возвращаемого типа<br /><br /> *x* = ± ∞<br /><br /> *x* = NaN|Вызывает **FE_INVALID** и возвращает ноль (0).|

## <a name="remarks"></a>Remarks

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **лринт** и **ллринт** , которые принимают **`float`** **`long double`** типы и. В программе на языке C **лринт** и **ллринт** всегда принимают **`double`** .

Если *x* не представляет эквивалент целочисленного значения с плавающей запятой, эти функции вызывают **FE_INEXACT**.

**Конкретно для Майкрософт**: Если результат находится вне диапазона возвращаемого типа или если параметр является NaN или бесконечностью, то возвращаемое значение определяется реализацией. Компилятор Майкрософт возвращает нулевое значение (0).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**лринт**, **лринтф**, **лринтл**, **ллринт**, **ллринтф**, **ллринтл**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
