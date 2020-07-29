---
title: cos, cosf, cosl
ms.date: 6/5/2020
api_name:
- cos
- cosf
- cosl
- _o_cos
- _o_cosf
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
- cos
- cosf
- cosl
helpviewer_keywords:
- cosines
- cosl function
- calculating cosine
- cosf function
- cos function
- trigonometric functions
- cosines, calculating
ms.assetid: ae90435e-6b68-4a47-a81f-be87d5c08f16
ms.openlocfilehash: ee5cb2c3a05514b4f10f73a2b27199b8e3a5ac4b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221930"
---
# <a name="cos-cosf-cosl"></a>cos, cosf, cosl

Вычисляет косинус.

## <a name="syntax"></a>Синтаксис

```C
double cos( double x );
float cosf( float x );
long double cosl( long double x );
```

```cpp
float cos( float x );  // C++ only
long double cos( long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Угол в радианах.

## <a name="return-value"></a>Возвращаемое значение

Косинус *x*. Если значение *x* больше или равно 263 или меньше или равно-263, то происходит отрицательное значение в результате.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± КНАН, С|нет|**_DOMAIN**|
|± INF|**Недопустимый**|**_DOMAIN**|

## <a name="remarks"></a>Remarks

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **COS** , которые принимают и возвращают **`float`** **`long double`** значения или. В программе на языке C функция **COS** всегда принимает и возвращает **`double`** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок C|Обязательный заголовок C++|
|-------------|---------------------|-|
|**COS**, **cosh**, **cosf**|\<math.h>|\<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в [sin, sinf, sinl](sin-sinf-sinl.md).

## <a name="see-also"></a>См. также раздел

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIcos](../../c-runtime-library/cicos.md)<br/>
