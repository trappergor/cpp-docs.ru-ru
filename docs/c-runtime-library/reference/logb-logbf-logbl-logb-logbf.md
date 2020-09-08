---
title: logb, logbf, logbl, _logb, _logbf
description: Справочник по API для logb, логбф, логбл, _logb и _logbf; который извлекает значение экспоненты для аргумента с плавающей запятой.
ms.date: 9/1/2020
api_name:
- logb
- _logb
- _logbl
- logbf
- _logbf
- logbl
- _o__logb
- _o_logb
- _o_logbf
- _o_logbl
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
- logb
- logbl
- _logb
- _logbf
- logbf
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
ms.openlocfilehash: 1131fda94e4748d2fb2f2197f68966aaacc11d05
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556218"
---
# <a name="logb-logbf-logbl-_logb-_logbf"></a>logb, logbf, logbl, _logb, _logbf

Извлекает значение экспоненты для аргумента с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double logb(
   double x
);
float logb(
   float x
); // C++ only
long double logb(
   long double x
); // C++ only
float logbf(
   float x
);
long double logbl(
   long double x
);
double _logb(
   double x
);
float _logbf(
   float x
);
#define logb(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

**logb** возвращает Несмещенное значение экспоненты *x* как целое число со знаком, представленное в виде значения с плавающей запятой.

## <a name="remarks"></a>Примечания

Функции **logb** извлекают экспоненциальное значение аргумента с плавающей запятой *x*, как если бы *x* были представлены с бесконечным диапазоном. Если аргумент *x* денормализован, он рассматривается как нормализованный.

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **logb** , которые принимают и возвращают **`float`** **`long double`** значения или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **logb** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `logb()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± КНАН, С|Нет|_DOMAIN|
|± 0|ZERODIVIDE|_SING|

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_logb**|\<float.h>|
|**logb**, **логбф**, **логбл**, **_logbf**|\<math.h>|
|макрос **logb** | \<tgmath.h> |

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Дополнительно

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
