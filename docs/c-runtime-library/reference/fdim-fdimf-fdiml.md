---
title: fdim, fdimf, fdiml
description: Справочник по API для фдим, fdimf и фдимл; который определяет положительную разность между двумя значениями.
ms.date: 9/1/2020
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
ms.openlocfilehash: 406fc5cfe543aa0865760df9ff780c62e78510fc
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554790"
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

#define fdim(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Первое значение в вычитании.

*&*\
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
|*x* или *y* является NaN|NaN|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **фдим** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **фдим** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `fdim()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

За исключением обработки NaN, эта функция эквивалентна `fmax(x - y, 0)` .

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**фдим**, **fdimf**, **фдимл**|\<math.h>|\<cmath>|
|макрос **фдим** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
