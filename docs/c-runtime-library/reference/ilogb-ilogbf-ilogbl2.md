---
title: ilogb, ilogbf, ilogbl2
ms.date: 04/05/2018
api_name:
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
ms.openlocfilehash: 6feea7a242a066f669429944226f4ca6022505b6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232525"
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb, ilogbf, ilogbl

Возвращает целое число, представляющее несмещенный порядок по основанию 2 для заданного значения.

## <a name="syntax"></a>Синтаксис

```C
int ilogb(
   double x
);

int ilogb(
   float x
); //C++ only

int ilogb(
   long double x
); //C++ only

int ilogbf(
   float x
);

int ilogbl(
   long double x
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Указанное значение.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвратите значение *x* 2 в качестве **`signed int`** значения.

В противном случае возвращает одно из следующих значений, определенное в \<math.h> :

|Входные данные|Результат|
|-----------|------------|
|± 0|FP_ILOGB0|
|± INF, ± NaN, неопределенное|FP_ILOGBNAN|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Remarks

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **илогб** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C **илогб** всегда принимает и возвращает **`double`** .

Вызов этой функции аналогичен вызову эквивалентной функции **logb** , а затем приведению возвращаемого значения к **`int`** .

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**илогб**, **илогбф**, **илогбл**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb, logbf, logbl, _logb, _logbf](logb-logbf-logbl-logb-logbf.md)<br/>
