---
title: nearbyint, nearbyintf, nearbyintl
description: Справочник по API для неарбинт, неарбинтф и неарбинтл; что Округляет указанное значение с плавающей запятой до целого числа и возвращает это значение в формате с плавающей запятой.
ms.date: 9/1/2020
api_name:
- nearbyint
- nearbyintf
- nearbyintl
- _o_nearbyint
- _o_nearbyintf
- _o_nearbyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
ms.openlocfilehash: 9717559518032c6f1f2126c7ded7cb90603bce64
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556389"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

Округляет заданное значение с плавающей запятой до целого числа и возвращает это значение в формате с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
#define nearbyint( X ) // Requires C11 or higher

float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>Параметры

*x*\
Значение для округления.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает значение *x*, округленное до ближайшего целого числа, используя текущий формат округления, сообщаемый [fegetround](fegetround-fesetround2.md). В противном случае функция может вернуть одно из следующих значений:

|Проблема|Возвращает|
|-----------|------------|
|*x* = ± бесконечности|± Бесконечности, без изменений|
|*x* = ± 0|± 0, без изменений|
|*x* = NaN|NaN|

Сообщения об ошибках не передаются в [_matherr](matherr.md); в частности, эта функция не сообщает об исключениях **FE_INEXACT** .

## <a name="remarks"></a>Примечания

Основное различие между этой функцией и [Печать](rint-rintf-rintl.md) заключается в том, что эта функция не вызывает неточного исключения с плавающей точкой.

Так как максимальные значения с плавающей запятой являются точными целыми числами, эта функция никогда не будет переполняться сама по себе; вместо этого выходные данные могут привести к переполнению возвращаемого значения в зависимости от используемой функции.

C++ допускает перегрузку, поэтому можно вызывать перегрузки **неарбинт** , которые принимают и возвращают **`float`** **`long double`** Параметры или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **неарбинт** всегда принимает два значения типа Double и возвращает значение типа Double.

При использовании \<tgmath.h> `nearbyint()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**неарбинт**, **неарбинтф**, **неарбинтл**|\<math.h>|\<cmath> или \<math.h>|
|макрос **неарбинт** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[Поддержка математических функций для чисел с плавающей запятой](../floating-point-support.md)<br/>
