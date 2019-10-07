---
title: fpclassify
ms.date: 04/05/2018
api_name:
- fpclassify
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
api_type:
- HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: e9b5aa1f7dc20cc920a51c2c36371eb907469875
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957064"
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

**fpclassify** возвращает целочисленное значение, указывающее класс с плавающей запятой аргумента *x*. В этой таблице показаны возможные значения, возвращаемые функцией **fpclassify**, \<определенной в Math. h >.

|Значение|Описание|
|-----------|-----------------|
|**FP_NAN**|Сигнальное, несигнальное или неопределенное значение NaN|
|**FP_INFINITE**|Положительная или отрицательная бесконечность|
|**FP_NORMAL**|Положительное или отрицательное нормализованное ненулевое значение|
|**FP_SUBNORMAL**|Положительное или отрицательное денормализованное значение|
|**FP_ZERO**|Положительное или отрицательное нулевое значение|

## <a name="remarks"></a>Примечания

В языке C **fpclassify** является макросом; в C++ **fpclassify** — это функция, перегруженная с помощью типов аргументов **float**, **Double**или **Long** **Double**. В обоих случаях возвращаемое значение зависит от действительного типа выражения аргумента, а не от промежуточного представления. Например, стандартное **Двойное** или **длинное** **Двойное** значение может стать бесконечным, нормальным или нулевым значением при преобразовании в тип **float**.

## <a name="requirements"></a>Требования

|Функция или макрос|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> или \<cmath>|

Макросы **fpclassify** и функции **fpclassify** соответствуют спецификациям ISO C99 и c++ 11. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
