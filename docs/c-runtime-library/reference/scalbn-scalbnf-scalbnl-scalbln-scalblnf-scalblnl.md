---
title: scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl
description: Справочник по API для scalbn, скалбнф, скалбнл, scalbln, скалблнф и скалблнл; который умножает число с плавающей запятой на целую степень `FLT_RADIX` .
ms.date: 9/1/2020
api_name:
- scalblnl
- scalbnl
- scalbnf
- scalblnf
- scalbn
- scalbln
- _o_scalbln
- _o_scalblnf
- _o_scalblnl
- _o_scalbn
- _o_scalbnf
- _o_scalbnl
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
- scalblnf
- scalbnl
- scalblnl
- scalbln
- scalbn
- scalbnf
helpviewer_keywords:
- scalbn function
- scalbln function
- scalblnl function
- scalbnl function
- scalbnf function
- scalblnf function
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
ms.openlocfilehash: 1a01811e5fcfb28c0557e0232d76649c867748b1
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556675"
---
# <a name="scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl"></a>scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl

Умножает число с плавающей запятой на целую степень числа FLT_RADIX.

## <a name="syntax"></a>Синтаксис

```C
double scalbn(
   double x,
   int exp
);
float scalbn(
   float x,
   int exp
);  // C++ only
long double scalbn(
   long double x,
   int exp
);  // C++ only
float scalbnf(
   float x,
   int exp
);
long double scalbnl(
   long double x,
   int exp
);

#define scalbn(X, INT) // Requires C11 or higher

double scalbln(
   double x,
   long exp
);

float scalblnf(
   float x,
   long exp
);
long double scalblnl(
   long double x,
   long exp
);

#define scalbln(X, LONG) // Requires C11 or higher

float scalbln(
   float x,
   long exp
);  // C++ only
long double scalbln(
   long double x,
   long exp
);  // C++ only
```

### <a name="parameters"></a>Параметры

*x*\
Значение с плавающей запятой.

*расширением*\
Целый показатель степени.

## <a name="return-value"></a>Возвращаемое значение

Функции **scalbn** возвращают значение *x* \* **FLT_RADIX**<sup>exp</sup> при успешном выполнении. При переполнении (в зависимости от знака *x*) **scalbn** возвращает +/- **HUGE_VAL**; значение **errno** перестройки передается в **ERANGE**.

Дополнительные сведения о параметрах **возврата и** возможностях, возвращающих ошибки, см. в разделе "переводится [, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)".

## <a name="remarks"></a>Примечания

**FLT_RADIX** определяется в \<float.h> качестве собственного системы счисления с плавающей запятой; в двоичных системах он имеет значение 2, а **scalbn** эквивалентно [ldexp](ldexp.md).

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **scalbn** и **scalbln** , которые принимают и возвращают **`float`** **`long double`** типы или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **scalbn** всегда принимает **`double`** и **`int`** и возвращает **`double`** , а **scalbln** всегда принимает, а и **`double`** **`long`** возвращает **`double`** .

При использовании \<tgmath.h> `scalbn()` `scalbln` макросов или тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**scalbn**, **скалбнф**, **скалбнл**, **scalbln**, **скалблнф**, **скалблнл**|\<math.h>|\<cmath>|
|макрос **scalbn () или scalbln** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_scalbn.c
// Compile using: cl /W4 crt_scalbn.c
#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 6.4, y;
   int p = 3;

   y = scalbn( x, p );
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );
}
```

### <a name="output"></a>Вывод

```Output
6.4 times FLT_RADIX to the power of 3 is 51.2
```

## <a name="see-also"></a>См. также

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
