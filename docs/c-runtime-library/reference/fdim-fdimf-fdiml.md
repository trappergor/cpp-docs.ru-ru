---
title: fdim, fdimf, fdiml
ms.date: 04/05/2018
api_name:
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
ms.openlocfilehash: 1a7bbeaf77c94f620a82f77fb1aad3c71c34f2ef
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221917"
---
# <a name="fdim-fdimf-fdiml"></a>fdim, fdimf, fdiml

Определяет положительную разность между первым и вторым значениями.

## <a name="syntax"></a>Синтаксис

```C
double fdim(
   double x,
   double y
);

float fdim(
   float x,
   float y
); //C++ only

long double fdim(
   long double x,
   long double y
); //C++ only

float fdimf(
   float x,
   float y
);

long double fdiml(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Первое значение в вычитании.

*&*<br/>
Второе значение в вычитании.

## <a name="return-value"></a>Возвращаемое значение

Возвращает положительную разность между *x* и *y*:

|Возвращаемое значение|Сценарий|
|------------------|--------------|
|x-y|если x > y|
|0|если x <= y|

В случае неудачи может возвращать одну из следующих ошибок:

|Проблема|Возвращает|
|-----------|------------|
|Ошибка переполнения диапазона|+HUGE_VAL, +HUGE_VALF или +HUGE_VALL|
|Ошибка недостаточного заполнения диапазона|правильное значение (после округления)|
|*x* или *y* является NaN|Не число|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Remarks

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **фдим** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C **фдим** всегда принимает и возвращает **`double`** .

За исключением обработки NaN, эта функция эквивалентна `fmax(x - y, 0)` .

## <a name="requirements"></a>Требования

|Компонент|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**фдим**, **fdimf**, **фдимл**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
