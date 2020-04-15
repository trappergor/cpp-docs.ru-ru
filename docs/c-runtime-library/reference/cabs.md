---
title: _cabs
ms.date: 4/2/2020
api_name:
- _cabs
- _o__cabs
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
- _cabs
helpviewer_keywords:
- cabs function
- absolute values
- _cabs function
- calculating absolute values
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
ms.openlocfilehash: e77e1811cb6f002c06e514b5f737b8a92ea84282
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333683"
---
# <a name="_cabs"></a>_cabs

Вычисляет абсолютное значение комплексного числа.

## <a name="syntax"></a>Синтаксис

```C
double _cabs(
   struct _complex z
);
```

### <a name="parameters"></a>Параметры

*Z*<br/>
Комплексное число.

## <a name="return-value"></a>Возвращаемое значение

**_cabs** возвращает абсолютную ценность своего аргумента в случае успеха. На переполнении, **_cabs** возвращает **HUGE_VAL** и устанавливает **errno** к **ERANGE**. Изменить обработку ошибок можно с помощью функции [_matherr](matherr.md).

## <a name="remarks"></a>Remarks

Функция **_cabs** вычисляет абсолютное значение сложного числа, которое должно быть структурой типа [_complex.](../../c-runtime-library/standard-types.md) Структура *z* состоит из реального компонента *x* и воображаемого компонента *y.* Призыв к **_cabs** производит значение, эквивалентное выражению. `sqrt( z.x * z.x + z.y * z.y )`

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_cabs**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_cabs.c
// Using _cabs, this program calculates
// the absolute value of a complex number.

#include <math.h>
#include <stdio.h>

int main( void )
{
   struct _complex number = { 3.0, 4.0 };
   double d;

   d = _cabs( number );
   printf( "The absolute value of %f + %fi is %f\n",
           number.x, number.y, d );
}
```

```Output
The absolute value of 3.000000 + 4.000000i is 5.000000
```

## <a name="see-also"></a>См. также раздел

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)
