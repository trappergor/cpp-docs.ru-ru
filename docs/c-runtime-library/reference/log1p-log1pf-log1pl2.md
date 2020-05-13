---
title: log1p, log1pf, log1pl2
ms.date: 4/2/2020
api_name:
- log1p
- log1pf
- log1pl
- _o_log1p
- _o_log1pf
- _o_log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
ms.openlocfilehash: 21bba72b204f975b806e43cdc6d36d8efa173b9b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911429"
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl

Вычисляет натуральный логарифм суммы указанного значения и 1.

## <a name="syntax"></a>Синтаксис

```C
double log1p(
   double x
);

float log1p(
   float x
); //C++ only

long double log1p(
   long double x
); //C++ only

float log1pf(
   float x
);

long double log1pl(
   long double x
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Аргумент с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает натуральный (по основанию*e*) журнал (*x* + 1).

В случае неудачи может возвращать одно из следующих значений:

|Входные данные|Результат|Исключение SEH|errno|
|-----------|------------|-------------------|-----------|
|+inf|+inf|||
|Денормализованные числа|Так же, как и для входных данных|UNDERFLOW||
|± 0|Так же, как и для входных данных|||
|-1|-inf|DIVBYZERO|ERANGE|
|< –1|не число|INVALID|EDOM|
|-inf|не число|INVALID|EDOM|
|± SNaN|Так же, как и для входных данных|INVALID||
|± КНАН, неопределенное|Так же, как и для входных данных|||

Значение **возврата** устанавливается РАВНым ERANGE, если *x* =-1. Значение **возврата** устанавливается равным **Едом** , если *x* <-1.

## <a name="remarks"></a>Remarks

Функции **log1p** могут быть более точными, чем `log(x + 1)` использование, когда *x* приближается к 0.

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **log1p** , которые принимают и возвращают типы **float** и **Long** **Double** . В программе на языке C **log1p** всегда принимает и возвращает значение **типа Double**.

Если *x* является естественным числом, эта функция возвращает логарифм факториала (*x* -1).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
