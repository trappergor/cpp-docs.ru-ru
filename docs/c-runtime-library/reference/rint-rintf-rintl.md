---
title: rint, rintf, rintl
description: Справочник по API для печать, ринтф и rintl; который Округляет значение с плавающей запятой до ближайшего целого числа в формате с плавающей запятой.
ms.date: 9/1/2020
api_name:
- rintf
- rintl
- rint
- _o_rint
- _o_rintf
- _o_rintl
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
- rintf
- rintl
- rint
helpviewer_keywords:
- rintf function
- rint function
- rintl function
ms.assetid: 312ae3e6-278c-459a-9393-11b8f87d9184
ms.openlocfilehash: 1ed1fa279694d3df75db5963e5a571d58299e415
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555349"
---
# <a name="rint-rintf-rintl"></a>rint, rintf, rintl

Округляет значение с плавающей запятой до ближайшего целого числа в формате с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double rint( double x );
float rintf( float x );
long double rintl( long double x );
#define rint(X) // Requires C11 or higher

float rint( float x );  // C++ only
long double rint( long double x );  // C++ only
```

### <a name="parameters"></a>Параметры

*x*\
Округляемое значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **Печать** возвращают значение с плавающей запятой, представляющее ближайшее целое число до *x*. Среднее значение округляется в соответствии с текущим значением режима округления с плавающей запятой, аналогично функциям **неарбинт** . В отличие от функций **неарбинт** , функции **печать** могут вызывать **FE_INEXACT** исключение с плавающей запятой, если результат отличается от значения аргумента. Ошибки не возвращаются.

|Входные данные|Исключение SEH|**_matherr** Об|
|-----------|-------------------|--------------------------|
|± ∞, КНАН, ТО ЕСТЬ|нет|нет|
|Денормализованные числа|EXCEPTION_FLT_UNDERFLOW|нет|

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **Печать** , которые принимают и возвращают **`float`** **`long double`** значения и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **Печать** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `rint()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**Печать**, **ринтф**, **rintl**|\<math.h>|\<cmath>|
|макрос **Печать** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_rint.c
// Build with: cl /W3 /Tc crt_rint.c
// This example displays the rounded results of
// the floating-point values 2.499999, -2.499999,
// 2.8, -2.8, 2.5 and -2.5.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.499999;
   float y = 2.8f;
   long double z = 2.5;

   printf("rint(%f) is %.0f\n", x, rint (x));
   printf("rint(%f) is %.0f\n", -x, rint (-x));
   printf("rintf(%f) is %.0f\n", y, rintf(y));
   printf("rintf(%f) is %.0f\n", -y, rintf(-y));
   printf("rintl(%Lf) is %.0Lf\n", z, rintl(z));
   printf("rintl(%Lf) is %.0Lf\n", -z, rintl(-z));
}
```

```Output
rint(2.499999) is 2
rint(-2.499999) is -2
rintf(2.800000) is 3
rintf(-2.800000) is -3
rintl(2.500000) is 3
rintl(-2.500000) is -3
```

## <a name="see-also"></a>См. также

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
[lround, lroundf, lroundl, llround, llroundf, llroundl](lround-lroundf-lroundl-llround-llroundf-llroundl.md)<br/>
[nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint](rint-rintf-rintl.md)<br/>
