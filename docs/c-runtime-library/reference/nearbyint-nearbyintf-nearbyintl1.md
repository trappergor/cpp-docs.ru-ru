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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 92e3a744ef8069d45733c06b7a2681905c3eab55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338591"
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

В случае успеха, возвращает *сяк,* округляется до ближайшего целых, используя текущий формат округления, как сообщает [fegetround](fegetround-fesetround2.md). В противном случае функция может вернуть одно из следующих значений:

|Проблемы|Возвращает|
|-----------|------------|
|*х* -ИНФИНИОНТИЯ|ИНФИНЕАНТИЯ, неизмененная|
|*х* 0 евро|No0, неизмененный|
|*х* - NaN|NaN|

Ошибки не сообщаются через [_matherr;](matherr.md) в частности, эта функция не сообщает о каких-либо **FE_INEXACT** исключениях.

## <a name="remarks"></a>Remarks

Основное различие между этой функцией и [rint](rint-rintf-rintl.md) заключается в том, что эта функция не поднимает неточное исключение плавающей точки.

Так как максимальные значения с плавающей запятой являются точными целыми числами, эта функция никогда не будет переполняться сама по себе; вместо этого выходные данные могут привести к переполнению возвращаемого значения в зависимости от используемой функции.

СЗ позволяет перегружать, так что вы можете вызвать перегрузки **поблизости,** которые принимают и возвращают **поплавок** или **длинные** **двойные** параметры. В программе **C, nearbyint** всегда принимает 2 двойных значения и возвращает двойное значение.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**nearbyint**, **nearbyintf**, **nearbyintl**|\<math.h>|\<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[Поддержка математических функций для чисел с плавающей запятой](../floating-point-support.md)<br/>
