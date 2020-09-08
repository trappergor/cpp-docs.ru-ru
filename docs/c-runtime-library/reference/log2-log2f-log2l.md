---
title: log2, log2f, log2l
description: Справочник по API для log2, log2f и log2l; , который определяет двоичный логарифм указанного значения (основание 2).
ms.date: 9/1/2020
api_name:
- log2
- log2l
- log2f
- _o_log2
- _o_log2f
- _o_log2l
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
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
ms.openlocfilehash: 37319560891dbd64030495750aaf347d9dedd7e7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555362"
---
# <a name="log2-log2f-log2l"></a>log2, log2f, log2l

Определяет двоичный логарифм (по основанию 2) для указанного значения.

## <a name="syntax"></a>Синтаксис

```C
double log2(
   double x
);

float log2(
   float x
); //C++ only

long double log2(
   long double x
); //C++ only

float log2f(
   float x
);

long double log2l(
   long double x
);

#define log2(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Значение, для которого вычисляется логарифм по основанию 2.

## <a name="return-value"></a>Возвращаемое значение

При успешном выполнении возвращает значение log2 *x*.

В случае неудачи может возвращать одно из следующих значений:

|Проблема|Возвращает|
|-----------|------------|
|*x* < 0|NaN|
|*x* = ± 0|-INFINITY|
|*x* = 1|+0|
|+INFINITY|+INFINITY|
|Не число|Не число|
|ошибка домена|NaN|
|Ошибка полюса|-HUGE_VAL, -HUGE_VALF или -HUGE_VALL|

Сообщает об ошибках, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Если *x* является целым числом, эта функция фактически возвращает отсчитываемый от нуля индекс наиболее значимого 1 бита *x*.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**log2**, **log2f**, **log2l**|\<math.h>|\<cmath>|
|макрос **log2** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
