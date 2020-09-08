---
title: round, roundf, roundl
description: Справочник по API для Round, раундф и Round; который Округляет значение с плавающей запятой до ближайшего целого числа.
ms.date: 9/1/2020
api_name:
- round
- roundl
- roundf
- _o_round
- _o_roundf
- _o_roundl
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
- roundf
- roundl
- round
helpviewer_keywords:
- roundl function
- round function
- roundf function
ms.assetid: 6be90877-193c-4b80-a32b-c3eca33f9c6f
ms.openlocfilehash: 0a7e47dd3a528e45abc8247a64bf5c4d81164e95
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556649"
---
# <a name="round-roundf-roundl"></a>round, roundf, roundl

Округляет заданное значение с плавающей запятой до ближайшего целого.

## <a name="syntax"></a>Синтаксис

```C
double round(
   double x
);
float round(
   float x
);  // C++ only
long double round(
   long double x
);  // C++ only
float roundf(
   float x
);
long double roundl(
   long double x
);
#define round(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*x*\
Округляемое значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Функции **Round** возвращают значение с плавающей запятой, представляющее ближайшее целое число к *x*. Промежуточные значения округляются в сторону от нуля, независимо от настройки режима округления чисел с плавающей запятой. Ошибки не возвращаются.

|Входные данные|Исключение SEH|Исключение Matherr|
|-----------|-------------------|-----------------------|
|± **КНАН**, **с**|нет|**_DOMAIN**|

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **Round** , которые принимают и возвращают **`float`** **`long double`** значения и. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, функция **Round** всегда принимает и возвращает **`double`** .

При использовании \<tgmath.h> `round()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**Round**, **раундф**, **Round**|\<math.h>|
|**круглый** макрос | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_round.c
// Build with: cl /W3 /Tc crt_round.c
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

   printf("round(%f) is %.0f\n", x, round(x));
   printf("round(%f) is %.0f\n", -x, round(-x));
   printf("roundf(%f) is %.0f\n", y, roundf(y));
   printf("roundf(%f) is %.0f\n", -y, roundf(-y));
   printf("roundl(%Lf) is %.0Lf\n", z, roundl(z));
   printf("roundl(%Lf) is %.0Lf\n", -z, roundl(-z));
}
```

```Output
round(2.499999) is 2
round(-2.499999) is -2
roundf(2.800000) is 3
roundf(-2.800000) is -3
roundl(2.500000) is 3
roundl(-2.500000) is -3
```

## <a name="see-also"></a>См. также

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
[lround, lroundf, lroundl, llround, llroundf, llroundl](lround-lroundf-lroundl-llround-llroundf-llroundl.md)<br/>
[nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint, rintf, rintl](rint-rintf-rintl.md)<br/>
