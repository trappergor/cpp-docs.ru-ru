---
title: fpclassify
ms.date: 04/05/2018
apiname:
- fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: 626e356cf61415e4f8212a8a12d90a72fe4576bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613880"
---
# <a name="fpclassify"></a>fpclassify

Возвращает значение, указывающее классификацию числа с плавающей запятой для аргумента.

## <a name="syntax"></a>Синтаксис

```C
int fpclassify(
   /* floating-point */ x
);

int fpclassify(
   float x
); // C++ only

int fpclassify(
   double x
); // C++ only

int fpclassify(
   long double x
); // C++ only

```

### <a name="parameters"></a>Параметры

*x*<br/>
Проверяемое значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

**fpclassify** возвращает целочисленное значение, указывающее класс с плавающей запятой аргумента *x*. В этой таблице приведены возможные значения, возвращаемые **fpclassify**, определенный в \<math.h >.

|Значение|Описание|
|-----------|-----------------|
|**FP_NAN**|Сигнальное, несигнальное или неопределенное значение NaN|
|**FP_INFINITE**|Положительная или отрицательная бесконечность|
|**FP_NORMAL**|Положительное или отрицательное нормализованное ненулевое значение|
|**FP_SUBNORMAL**|Положительное или отрицательное денормализованное значение|
|**FP_ZERO**|Положительное или отрицательное нулевое значение|

## <a name="remarks"></a>Примечания

В языке C **fpclassify** представляет собой макрос, а в C++, **fpclassify** — это функция, перегружаемая с использованием аргументов типа **float**, **двойные**, или **long** **двойные**. В обоих случаях возвращаемое значение зависит от действительного типа выражения аргумента, а не от промежуточного представления. Например, обычный **двойные** или **long** **двойные** может становиться бесконечным, denormal или нулевым значением при преобразовании в значение **float**.

## <a name="requirements"></a>Требования

|Функция или макрос|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> или \<cmath>|

**Fpclassify** макрос и **fpclassify** функции соответствуют стандарту ISO C99 и C ++ 11 спецификаций. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
