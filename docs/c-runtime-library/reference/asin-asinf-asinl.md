---
title: asin, asinf, asinl
description: Справочник по API для ASIN, асинф и ASIN; который вычисляет Арксинус значения с плавающей запятой.
ms.date: 08/31/2020
api_name:
- asinf
- asinl
- asin
- _o_asin
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
- asin
- asinl
- asinf
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
ms.openlocfilehash: 7167debcfb605ab05720d9441943439ea9982324
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556662"
---
# <a name="asin-asinf-asinl"></a>asin, asinf, asinl

Вычисляет арксинус.

## <a name="syntax"></a>Синтаксис

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
#define asin(X) // Requires C11 or higher

float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*\
Значение, арксинус которого необходимо вычислить.

## <a name="return-value"></a>Возвращаемое значение

Функция **ASIN** Возвращает арксинус (функцию обратного синуса) *x* в диапазоне от-π/2 до π/2 радиан.

По умолчанию, если *x* меньше-1 или больше 1, **ASIN** возвращает неопределенное значение.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± ∞|**Недопустимый**|**_DOMAIN**|
|± **КНАН**, **с**|нет|**_DOMAIN**|
|&#124;x&#124;>1|**Недопустимый**|**_DOMAIN**|

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **ASIN** со **`float`** значениями и **`long double`** . В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **ASIN** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `asin()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------|-|
|**ASIN**, **асинф**, **ASIN**|\<math.h>|\<cmath> или \<math.h>|
|макрос **ASIN ()** | \<tgmath.h> ||

## <a name="example"></a>Пример

Дополнительные сведения см. в разделе [acos, acosf, acosl](acos-acosf-acosl.md).

## <a name="see-also"></a>Дополнительно

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
