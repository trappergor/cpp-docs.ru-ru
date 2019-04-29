---
title: asin, asinf, asinl
ms.date: 04/05/2018
apiname:
- asinf
- asinl
- asin
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
ms.openlocfilehash: 20a2ffc37ea666207b9558cb5c282c414cfd4838
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347968"
---
# <a name="asin-asinf-asinl"></a>asin, asinf, asinl

Вычисляет арксинус.

## <a name="syntax"></a>Синтаксис

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
```

```cpp
float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение, арксинус которого необходимо вычислить.

## <a name="return-value"></a>Возвращаемое значение

**Asin** функция возвращает арксинус (функцию обратного синуса) *x* в диапазоне - π/2 до радианы π/2.

По умолчанию если *x* меньше -1 или больше 1, **asin** возвращает неопределенное.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± ∞|**НЕДОПУСТИМЫЙ**|**_DOMAIN**|
|± **QNAN**, **IND**|Нет|**_DOMAIN**|
|&#124;x&#124;>1|**НЕДОПУСТИМЫЙ**|**_DOMAIN**|

## <a name="remarks"></a>Примечания

Так как C++ допускает перегрузку, можно вызывать перегрузки **asin** с **float** и **long** **двойные** значения. В программе на языке C **asin** всегда принимает и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------|-|
|**ASIN**, **asinf**, **asinl**|\<math.h>|\<cmath> или \<math.h>|

## <a name="example"></a>Пример

Дополнительные сведения см. в разделе [acos, acosf, acosl](acos-acosf-acosl.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
