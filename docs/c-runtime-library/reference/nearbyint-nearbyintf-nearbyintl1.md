---
title: nearbyint, nearbyintf, nearbyintl
ms.date: 4/2/2020
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
ms.openlocfilehash: 898544f5b191eb68e0ed6f17d7c3c7df849e8d11
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216860"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

Округляет заданное значение с плавающей запятой до целого числа и возвращает это значение в формате с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
```

```cpp
float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение для округления.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает значение *x*, округленное до ближайшего целого числа, используя текущий формат округления, сообщаемый [fegetround](fegetround-fesetround2.md). В противном случае функция может вернуть одно из следующих значений:

|Проблема|Возвращает|
|-----------|------------|
|*x* = ± бесконечности|± Бесконечности, без изменений|
|*x* = ± 0|± 0, без изменений|
|*x* = NaN|Не число|

Сообщения об ошибках не передаются в [_matherr](matherr.md); в частности, эта функция не сообщает об исключениях **FE_INEXACT** .

## <a name="remarks"></a>Remarks

Основное различие между этой функцией и [Печать](rint-rintf-rintl.md) заключается в том, что эта функция не вызывает неточного исключения с плавающей точкой.

Так как максимальные значения с плавающей запятой являются точными целыми числами, эта функция никогда не будет переполняться сама по себе; вместо этого выходные данные могут привести к переполнению возвращаемого значения в зависимости от используемой функции.

C++ допускает перегрузку, поэтому можно вызывать перегрузки **неарбинт** , которые принимают и возвращают **`float`** **`long double`** Параметры или. В программе на языке C **неарбинт** всегда принимает два значения типа Double и возвращает значение типа Double.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**неарбинт**, **неарбинтф**, **неарбинтл**|\<math.h>|\<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[Поддержка математических функций для чисел с плавающей запятой](../floating-point-support.md)<br/>
