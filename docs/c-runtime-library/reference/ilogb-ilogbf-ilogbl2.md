---
title: ilogb, ilogbf, ilogbl2
description: Справочник по API для илогб, илогбф и ilogbl2; Возвращает целое число, представляющее несмещенную базовую экспоненту указанного значения.
ms.date: 9/1/2020
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
ms.openlocfilehash: b27c329cca1edb9d30bb6b9b641f94d174c9c406
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556376"
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

#define ilogbl(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Указанное значение.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвратите значение *x* 2 в качестве **`signed int`** значения.

В противном случае возвращает одно из следующих значений, определенное в \<math.h> :

|Входные данные|Результат|
|-----------|------------|
|± 0|FP_ILOGB0|
|± INF, ± NaN, неопределенное|FP_ILOGBNAN|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **илогб** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **илогб** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `ilogb()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

Вызов этой функции аналогичен вызову эквивалентной функции **logb** , а затем приведению возвращаемого значения к **`int`** .

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**илогб**, **илогбф**, **илогбл**|\<math.h>|\<cmath>|
|макрос **илогб** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb, logbf, logbl, _logb, _logbf](logb-logbf-logbl-logb-logbf.md)<br/>
