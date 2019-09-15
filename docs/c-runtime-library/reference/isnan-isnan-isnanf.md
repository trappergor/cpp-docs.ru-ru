---
title: isnan, _isnan, _isnanf
ms.date: 01/31/2019
api_name:
- _isnan
- _isnanf
- isnan
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
ms.openlocfilehash: a0cc60fb80f8d5b78ec2947a87fde82a536b413c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953766"
---
# <a name="isnan-_isnan-_isnanf"></a>isnan, _isnan, _isnanf

Проверяет, является ли значение с плавающей запятой нечисловым значением (NAN).

## <a name="syntax"></a>Синтаксис

```C
int isnan(
   /* floating-point */ x
); /* C-only macro */

int _isnan(
   double x
);

int _isnanf(
   float x
); /* x64 only */

template <class T>
bool isnan(
   T x
) throw(); /* C++ only */
```

### <a name="parameters"></a>Параметры

*x*<br/>
Проверяемое значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

В языке C макрос **IsNaN** и функции **_isnan** и **_isnanf** возвращают ненулевое значение, если аргумент *x* является NaN; в противном случае они возвращают 0.

В C++функция шаблона **IsNaN** возвращает **значение true** , если аргумент *x* является NaN; в противном случае возвращается **значение false**.

## <a name="remarks"></a>Примечания

Поскольку значение NaN не сравнивается ни с одним другим значением NaN, необходимо использовать одну из этих функций или макросов для обнаружения одного значения. Значение NaN создается, если результат операции с плавающей запятой не может быть представлен в формате IEEE-754 с плавающей точкой для указанного типа. Сведения о том, как значение NaN представлено для вывода, см. в разделе [printf](printf-printf-l-wprintf-wprintf-l.md).

При компиляции как C++, макрос **IsNaN** не определен и вместо него определена функция шаблона **IsNaN** . Он ведет себя так же, как и макрос, но возвращает значение типа **bool** , а не целое число.

Функции **_isnan** и **_isnanf** являются специфичными для Microsoft. Функция **_isnanf** доступна только при компиляции для x64.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------------|-------------------------------|
|**IsNaN**, **_isnanf**|\<math.h>|\<math.h> или \<cmath>|
|**_isnan**|\<float.h>|\<float.h> или \<cfloat>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnormal](isnormal.md)<br/>
