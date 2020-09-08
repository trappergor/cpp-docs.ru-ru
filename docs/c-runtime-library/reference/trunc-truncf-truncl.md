---
title: trunc, truncf, truncl
description: Справочник по API для TRUNC, трункф, трункл; , который определяет ближайшее целое число, которое меньше или равно заданному значению с плавающей запятой.
ms.date: 9/1/2020
api_name:
- trunc
- truncf
- truncl
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
- trunc
- truncf
- truncl
- math/trunc
- math/truncf
- math/truncl
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
ms.openlocfilehash: f1f2fde95bb944aa461bb95a9ad30fac204552b9
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556636"
---
# <a name="trunc-truncf-truncl"></a>trunc, truncf, truncl

Определяют ближайшего целое число, которое меньше или равно заданному значению с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double trunc( double x );
long double truncl( long double x );
#define trunc(X) // Requires C11 or higher

long double trunc( long double x ); //C++ only
float trunc( float x ); //C++ only
```

### <a name="parameters"></a>Параметры

*x*\
Значение для усечения.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает целое значение *x*, округленное в сторону нуля.

В случае неудачи может возвращать одно из следующих значений:

|Проблема|Возвращает|
|-----------|------------|
|*x* = ± бесконечности|x|
|*x* = ± 0|x|
|*x* = NaN|NaN|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **TRUNC** , которые принимают и возвращают **`float`** **`long double`** типы и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **TRUNC** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `trunc()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

Поскольку наибольшими значениями с плавающей запятой являются целые числа, эта функция не будет переполняться сама по себе. Тем не менее можно вызвать переполнение этой функции, возвращая значение в целочисленный тип.

Можно также округлять в меньшую сторону, выполняя неявное преобразование из типа с плавающей запятой в целочисленный тип; однако это можно делать только со значениями, которые могут храниться в целевом типе.

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**TRUNC**, **трункф**, **трункл**|\<math.h>|\<cmath>|
|макрос **TRUNC** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[round, roundf, roundl](round-roundf-roundl.md)<br/>
