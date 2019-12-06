---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl
ms.date: 04/05/2018
api_name:
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
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
ms.openlocfilehash: c7831842eb4d3c1eef9c4c9e83bbddb557cec0e3
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857753"
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

|Проблема|Назад|
|-----------|------------|
|*x* находится за пределами диапазона возвращаемого типа<br /><br /> *x* = ± ∞<br /><br /> *x* = NaN|Вызывает **FE_INVALID** и возвращает ноль (0).|

## <a name="remarks"></a>Заметки

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **лринт** и **ллринт** , которые принимают типы **float** и **Long** **Double** . В программе на языке C **лринт** и **ллринт** всегда принимают значение **double**.

Если *x* не представляет эквивалент целочисленного значения с плавающей запятой, эти функции вызывают **FE_INEXACT**.

**Конкретно для Майкрософт**: Если результат находится вне диапазона возвращаемого типа или если параметр является NaN или бесконечностью, то возвращаемое значение определяется реализацией. Компилятор Майкрософт возвращает нулевое значение (0).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**лринт**, **лринтф**, **лринтл**, **ллринт**, **ллринтф**, **ллринтл**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также:

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
