---
title: exp2, exp2f, exp2l | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- exp2
- exp2f
- exp2l
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
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
dev_langs:
- C++
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69b7deb8e6e43ded0a3545bc1b33961d977eeb1f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="exp2-exp2f-exp2l"></a>exp2, exp2f, exp2l

Вычисляет 2 возникает с указанным значением.

## <a name="syntax"></a>Синтаксис

```C
double exp2(
   double x
);

float exp2(
   float x
);  // C++ only

long double exp2(
   long double x
); // C++ only

float exp2f(
   float x
);

long double exp2l(
   long double x
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение экспоненты.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает 2 в степени экспоненты *x*, то есть 2<sup>x</sup>. В противном случае он возвращает одно из следующих значений:

|Проблеми|Назад|
|-----------|------------|
|*x* = ±0|1|
|*x* = - INFINITY|+0|
|*x* = + бесконечность|+INFINITY|
|*x* = NaN|NaN|
|Ошибка переполнения диапазона|+HUGE_VAL, +HUGE_VALF или +HUGE_VALL|
|Ошибка недостаточного заполнения диапазона|Правильный результат, после округления|

Ошибки сообщаются, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **exp2** , принимающие и возвращающие **float** и **long double** типов. В программе на языке C **exp2** всегда принимает и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**EXP**, **expf**, **реш**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
