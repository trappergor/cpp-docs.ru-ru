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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 6283cffaa094af4484d48781b5bb92d0339d38d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341668"
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

В случае успеха возвращает округленное интегральное значение *x*.

|Проблемы|Возвращает|
|-----------|------------|
|*x* находится за пределами диапазона типа возврата<br /><br /> *х* х<br /><br /> *х* - NaN|Повышает **FE_INVALID** и возвращаетное ноль (0).|

## <a name="remarks"></a>Remarks

Из-за того, что СЗ позволяет перегружать, можно вызывать перегрузки и **llrint,** которые принимают **плавающие** и **длинные** **двойные** типы. **lrint** В программе C, **lrint** и **llrint** всегда принимают **двойной**.

Если *x* не представляет собой эквивалент плавающей точки интегрального значения, эти функции повышают **FE_INEXACT.**

**Специфика Microsoft:** Когда результат находится за пределами диапазона типа возврата, или когда параметр NaN или бесконечность, значение возврата определяется. Компилятор Майкрософт возвращает нулевое значение (0).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**lrint**, **lrintf**, **lrintl**, **llrint**, **llrintf**, **llrintl**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
