---
title: fma, fmaf, fmal
ms.date: 04/05/2018
apiname:
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
ms.openlocfilehash: a3b540a72c6f2fc2264d6366111831fbe2a02a6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529952"
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal

Перемножает два значения, добавляет к произведению третье значение и затем округляет результат без потери точности, вызванной промежуточным округлением.

## <a name="syntax"></a>Синтаксис

```C
double fma(
   double x,
   double y,
   double z
);

float fma(
   float  x,
   float  y,
   float z
); //C++ only

long double fma(
   long double  x,
   long double  y,
   long double z
); //C++ only

float fmaf(
   float  x,
   float  y,
   float z
);

long double fmal(
   long double  x,
   long double  y,
   long double z
);

```

### <a name="parameters"></a>Параметры

*x*<br/>
Первое значение для перемножения.

*y*<br/>
Второе значение для перемножения.

*z*<br/>
Значение для сложения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает `(x * y) + z`. Возвращаемое значение округляется с использованием текущего формата округления.

В случае неудачи может возвращать одно из следующих значений:

|Проблемы|Назад|
|-----------|------------|
|*x* = INFINITY, *y* = 0 или<br /><br /> *x* = 0, *y* = INFINITY|NaN|
|*x* или *y* = точное ± бесконечность, *z* = INFINITY с противоположным знаком|NaN|
|*x* или *y* = NaN|NaN|
|не (*x* = 0, *y*= неопределенное) и *z* = NaN<br /><br /> не (*x*= неопределенное значение, *y*= 0) и *z* = NaN|NaN|
|Ошибка переполнения диапазона|±HUGE_VAL, ±HUGE_VALF или ±HUGE_VALL|
|Ошибка недостаточного заполнения диапазона|правильное значение (после округления).|

Ошибки сообщаются, как указано в [_matherr](matherr.md).

## <a name="remarks"></a>Примечания

Так как C++ допускает перегрузку, можно вызывать перегрузки **fma** , принимающие и возвращающие **float** и **long** **двойные** типов. В программе на языке C **fma** всегда принимает и возвращает **двойные**.

Эта функция вычисляет значение с бесконечной точностью, после чего округляет результат.

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**FMA**, **fmaf**, **fmal**|\<math.h>|\<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
