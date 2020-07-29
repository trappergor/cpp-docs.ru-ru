---
title: cosh, coshf, coshl
ms.date: 4/2/2020
api_name:
- cosh
- coshf
- coshl
- _o_cosh
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
- cosh
- coshf
- coshl
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: fb171d622d5bc187342054a74e8aa19f83c3c560
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213610"
---
# <a name="cosh-coshf-coshl"></a>cosh, coshf, coshl

Вычисляет гиперболический косинус.

## <a name="syntax"></a>Синтаксис

```C
double cosh( double x );
float coshf( float x );
long double coshl( long double x );
```

```cpp
float cosh( float x );  // C++ only
long double cosh( long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Угол в радианах.

## <a name="return-value"></a>Возвращаемое значение

Гиперболический косинус для *x*.

По умолчанию, если результат слишком велик в вызове **cosh**, **кошф**или **кошл** , функция возвращает **HUGE_VAL** **и устанавливает значение** переводится в **ERANGE**.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± **КНАН**, **с**|нет|**_DOMAIN**|
|*x* ≥ 7.104760 e + 002|**НЕточность** + **Переполнение**|**ПОЛН**|

## <a name="remarks"></a>Remarks

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **cosh** , которые принимают и возвращают **`float`** **`long double`** значения или. В программе на языке C **cosh** всегда принимает и возвращает **`double`** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------|-|
|**кошф**, **косл**, **кошл**|\<math.h>|\<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример в [sinh, sinhf, sinhl](sinh-sinhf-sinhl.md).

## <a name="see-also"></a>См. также раздел

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
