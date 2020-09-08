---
title: fmod, fmodf, fmodl
description: Справочник по API для FMOD, фмодф и фмодл; для вычисления остатка с плавающей запятой.
ms.date: 9/1/2020
api_name:
- fmod
- fmodf
- fmodl
- _o_fmod
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
- fmod
- _fmodl
- fmodf
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmodl function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
ms.openlocfilehash: 2b610dec79c98b973af09f8efb147ad6797f7946
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556090"
---
# <a name="fmod-fmodf-fmodl"></a>fmod, fmodf, fmodl

Вычисляет остаток с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double fmod(
   double x,
   double y
);
float fmod(
   float x,
   float y
);  // C++ only
long double fmod(
   long double x,
   long double y
);  // C++ only
float fmodf(
   float x,
   float y
);
long double fmodl(
   long double x,
   long double y
);

#define fmod(X, Y) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*, *y*\
Значения с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

**FMOD** возвращает остаток от деления *x*y на значение с плавающей запятой  /  *y*. Если значение *y* равно 0,0, **FMOD** возвращает нетихом NaN. Сведения о представлении нескрытого числа NaN в семействе **printf** см. в разделе [printf](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Примечания

Функция **FMOD** вычисляет *f* y остатка с плавающей запятой *x*  /  *y* таким образом, что *x*  =  *i* \* *y*  +  *f*, где *i* является целым числом, *f* имеет тот же знак, что и *x*, а абсолютное значение *f* меньше, чем абсолютное значение *y*.

C++ допускает перегрузку, поэтому можно вызывать перегрузки **FMOD** , которые принимают и возвращают **`float`** **`long double`** значения и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **FMOD** всегда принимает два **`double`** аргумента и возвращает **`double`** .

При использовании \<tgmath.h> `fmod()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**FMOD**, **фмодф**, **фмодл**|\<math.h>|
|макрос **FMOD** | \<tgmath.h> |

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fmod.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = fmod( w, x );
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>См. также

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[_CIfmod](../../c-runtime-library/cifmod.md)<br/>
