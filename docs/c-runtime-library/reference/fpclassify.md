---
title: fpclassify | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da55cb87804d178d5a305ed466aa498de4bc1ee5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

**fpclassify** возвращает целочисленное значение, указывающее класс с плавающей запятой аргумента *x*. В этой таблице приведены возможные значения, возвращенные **fpclassify**, определенного в \<math.h >.

|Значение|Описание|
|-----------|-----------------|
|**FP_NAN**|Сигнальное, несигнальное или неопределенное значение NaN|
|**FP_INFINITE**|Положительная или отрицательная бесконечность|
|**FP_NORMAL**|Положительное или отрицательное нормализованное ненулевое значение|
|**FP_SUBNORMAL**|Положительное или отрицательное денормализованное значение|
|**FP_ZERO**|Положительное или отрицательное нулевое значение|

## <a name="remarks"></a>Примечания

В языке C **fpclassify** представляет собой макрос; в C++ **fpclassify** — это функция, перегружен, с помощью аргумента типа **float**, **двойные**, или **длинные** **двойные**. В обоих случаях возвращаемое значение зависит от действительного типа выражения аргумента, а не от промежуточного представления. Например, обычный **двойные** или **длинные** **двойные** значение может стать бесконечности, denormal или нуля значение, при преобразовании **float**.

## <a name="requirements"></a>Требования

|Функция или макрос|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> или \<cmath>|

**Fpclassify** макрос и **fpclassify** функции соответствует ISO C99 и C ++ 11 спецификации. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
