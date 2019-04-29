---
title: log1p, log1pf, log1pl2
ms.date: 04/05/2018
apiname:
- log1p
- log1pf
- log1pl
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 2ac864d7e28823c95b0202c0a8f2454d03c64aff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285990"
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

В случае успешного выполнения возвращает натуральный (базовый -*e*) из системы (*x* + 1).

В случае неудачи может возвращать одно из следующих значений:

|Входные данные|Результат|Исключение SEH|errno|
|-----------|------------|-------------------|-----------|
|+inf|+inf|||
|Денормализованные числа|Аналогично входным данным|UNDERFLOW||
|±0|Аналогично входным данным|||
|-1|-inf|DIVBYZERO|ERANGE|
|< –1|nan|INVALID|EDOM|
|-inf|nan|INVALID|EDOM|
|±SNaN|Аналогично входным данным|INVALID||
|±QNaN, неопределенное|Аналогично входным данным|||

**Errno** значение задается значение ERANGE, если *x* = -1. **Errno** присваивается значение **EDOM** Если *x* < -1.

## <a name="remarks"></a>Примечания

**Log1p** функции могут быть более точен, чем `log(x + 1)` при *x* , близких к 0.

Так как C++ допускает перегрузку, можно вызывать перегрузки **log1p** , принимающие и возвращающие **float** и **long** **двойные** типов. В программе на языке C **log1p** всегда принимает и возвращает **двойные**.

Если *x* является натуральным числом, эта функция возвращает логарифм факториала (*x* - 1).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
