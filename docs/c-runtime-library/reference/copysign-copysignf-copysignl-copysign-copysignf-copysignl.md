---
title: copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl
description: Ссылка API для возвращения значения с величиной одного аргумента и знака другого с помощью кописигн ()
ms.date: 9/1/2020
api_name:
- copysignf
- copysignl
- _copysignl
- _copysign
- _copysignf
- copysign
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
- _copysignl
- copysign
- copysignf
- _copysign
- copysignl
- _copysignf
helpviewer_keywords:
- copysignl function
- _copysignl function
- copysign function
- _copysignf function
- _copysign function
- copysignf function
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
ms.openlocfilehash: 8f9ffe56e82f6a82da15fde3f8efea60fc1c0f9f
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554868"
---
# <a name="copysign-copysignf-copysignl-_copysign-_copysignf-_copysignl"></a>copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl

Возвращает значение, которое имеет абсолютное значение одного аргумента и знак другого.

## <a name="syntax"></a>Синтаксис

```C
double copysign(
   double x,
   double y
);
float copysign(
   float x,
   float y
); // C++ only
long double copysign(
   long double x,
   long double y
); // C++ only
float copysignf(
   float x,
   float y
); // C++ only
long double copysignl(
   long double x,
   long double y
); // C++ only
double _copysign(
   double x,
   double y
);
long double _copysignl(
   long double x,
   long double y
);
#define copysign(X, Y) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Значение с плавающей запятой, которое возвращается как абсолютное значение результата.

*&*\
Значение с плавающей запятой, которое возвращается как знак результата.

[Подпрограммы поддержки чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)

## <a name="return-value"></a>Возвращаемое значение

Функции **кописигн** возвращают значение с плавающей запятой, объединяющее величину *x* и знак *y*. Ошибки не возвращаются.

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **кописигн** , которые принимают и возвращают **`float`** **`long double`** значения или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **кописигн** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `copysign()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_copysign**|\<float.h>|
|**кописигн**, **кописигнф**, **кописигнл**, **_copysignf**, **_copysignl**|\<math.h>|
|макрос **кописигн** | \<tgmath.h> |

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[_chgsign, _chgsignf, _chgsignl](chgsign-chgsignf-chgsignl.md)<br/>
