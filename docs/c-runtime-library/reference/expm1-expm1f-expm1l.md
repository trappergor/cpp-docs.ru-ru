---
title: expm1, expm1f, expm1l
description: Справочник по API для expm1, expm1f и expm1; который вычисляет экспоненциальное значение по основанию e, минус единицу.
ms.date: 9/1/2020
api_name:
- expm1l
- expm1
- expm1f
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
- expm1l
- expm1
- expm1f
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
ms.openlocfilehash: 6d352e91d895cd63c7134faff90bc1bc43a50708
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556506"
---
# <a name="expm1-expm1f-expm1l"></a>expm1, expm1f, expm1l

Вычисляет экспоненту значения с основанием e минус один.

## <a name="syntax"></a>Синтаксис

```C
double expm1(
   double x
);
float expm1(
   float x
);  // C++ only
long double expm1(
   long double x
);  // C++ only
float expm1f(
   float x
);
long double expm1l(
   long double x
);
#define expm1(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Значение экспоненты с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **expm1** возвращают значение с плавающей запятой, представляющее e<sup>x</sup> -1 в случае успеха. При переполнении **expm1** возвращает значение **HUGE_VAL**, **expm1f** возвращает **HUGE_VALF**, **expm1l** возвращает **HUGE_VALL**, **а для** свойства "переводится" в **ERANGE**. Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **expm1** , которые принимают и возвращают **`float`** **`long double`** значения и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **expm1** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `expm1()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**expm1**, **expm1f**, **expm1l**|\<math.h>|
|макрос **expm1** | \<tgmath.h> |

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>
