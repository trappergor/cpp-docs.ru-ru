---
title: asin, asinf, asinl
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 424fee6995fae4a7f878054ede1bb85d33d1706d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334128"
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

Функция **осин** возвращает дугсин (обратную функцию синуса) *х* в диапазоне - от 2 до 2 рад.

По умолчанию, если *x* меньше -1 или больше, чем 1, **asin** возвращает сятворное время.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± ∞|**Недопустимый**|**_DOMAIN**|
|- **ЗНАН**, **IND**|Нет|**_DOMAIN**|
|&#124;x&#124;>1|**Недопустимый**|**_DOMAIN**|

## <a name="remarks"></a>Remarks

Поскольку СЗ допускает перегрузку, можно вызывать перегрузки **осин** с **поплавком** и **длинными** **двойными** значениями. В программе C, **asin** всегда берет и возвращает **двойной**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|-------------|---------------------|-|
|**асин**, **asinf**, **asinl**|\<math.h>|\<cmath> или \<math.h>|

## <a name="example"></a>Пример

Дополнительные сведения см. в разделе [acos, acosf, acosl](acos-acosf-acosl.md).

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
