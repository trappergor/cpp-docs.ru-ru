---
title: fmax, fmaxf, fmaxl
description: Справочник по API для FMAX, fmaxf и fmaxl; который определяет большее из двух числовых значений.
ms.date: 9/1/2020
api_name:
- fmax
- fmaxf
- fmaxl
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
- fmax
- fmaxf
- fmaxl
- math/fmax
- math/fmaxf
- math/fmaxl
helpviewer_keywords:
- fmax function
- fmaxf function
- fmaxl function
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
ms.openlocfilehash: 4f38db64b30598e7cfb4eb4d0f57dccf257dabc5
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556688"
---
# <a name="fmax-fmaxf-fmaxl"></a>fmax, fmaxf, fmaxl

Определяет большее из двух указанных числовых значений.

## <a name="syntax"></a>Синтаксис

```C
double fmax(
   double x,
   double y
);

float fmax(
   float x,
   float y
); //C++ only

long double fmax(
   long double x,
   long double y
); //C++ only

float fmaxf(
   float x,
   float y
);

long double fmaxl(
   long double x,
   long double y
);

#define fmax(X, Y) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Первое сравниваемое значение.

*&*\
Второе сравниваемое значение.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает большее значение *x* или *y*. Возвращает точное значение независимо от формы округления.

В случае неудачи может возвращать одно из следующих значений:

|Проблема|Возвращает|
|-----------|------------|
|*x* = NaN|*y*|
|*y* = NaN|*x*|
|*x* и *y* = NaN|NaN|

Эта функция не использует ошибки, указанные в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки FMAX, которые принимают и возвращают `float` `long double` типы и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, `fmax` всегда принимает и возвращает значение типа Double.

При использовании \<tgmath.h> `fmax()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**FMAX**, **fmaxf**, **fmaxl**|\<math.h>|\<cmath> или \<math.h>|
|макрос **FMAX** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[fmin, fminf, fminl](fmin-fminf-fminl.md)<br/>
