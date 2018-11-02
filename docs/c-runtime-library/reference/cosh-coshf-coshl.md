---
title: COSH, coshf, coshl
ms.date: 04/11/2018
apiname:
- cosh
- coshf
- coshl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 0f55e084e760cb6d04dbe7ec4fefb5e2ac1d79fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609538"
---
# <a name="cosh-coshf-coshl"></a>COSH, coshf, coshl

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

Гиперболический косинус *x*.

По умолчанию, если результат слишком велик в **cosh**, **coshf**, или **coshl** вызвать, функция возвращает **HUGE_VAL** и задает **errno** для **ERANGE**.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|Нет|**Д_ОМЕН ИМЯ**|
|*x* ≥ 7.104760e + 002|**НЕТОЧНЫЙ**+**ПЕРЕПОЛНЕНИЯ**|**ПЕРЕПОЛНЕНИЕ**|

## <a name="remarks"></a>Примечания

Так как C++ допускает перегрузку, можно вызывать перегрузки **cosh** , принимающие и возвращающие **float** или **long** **двойные** значения. В программе на языке C **cosh** всегда принимает и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------|-|
|**coshf**, **cosl**, **coshl**|\<math.h>|\<cmath> или \<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Ознакомьтесь с примером в [sinh, sinhf, sinhl](sinh-sinhf-sinhl.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
