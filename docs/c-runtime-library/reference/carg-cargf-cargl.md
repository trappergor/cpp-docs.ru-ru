---
title: carg, cargf, cargl
description: Справочник по API для Карг, каргф и Каргл; который получает аргумент комплексного числа с ветвью, повырезанной вдоль отрицательной реальной оси.
ms.date: 9/2/2020
api_name:
- carg
- cargf
- cargl
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- carg
- cargf
- cargl
- complex/carg
- complex/cargf
- complex/cargl
helpviewer_keywords:
- carg function
- cargf function
- cargl function
ms.assetid: 610d6a93-b929-46ab-a966-b77db0b804be
ms.openlocfilehash: 907694904b260c44dde84724c739c62dfe46dbde
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555817"
---
# <a name="carg-cargf-cargl"></a>carg, cargf, cargl

Извлекает аргумент комплексного числа с ветвью, вырезанной вдоль отрицательной реальной оси.

## <a name="syntax"></a>Синтаксис

```C
double carg(
   _Dcomplex z
);
float carg(
   _Fcomplex z
);  // C++ only
long double carg(
   _Lcomplex z
);  // C++ only
float cargf(
   _Fcomplex z
);
long double cargl(
   _Lcomplex z
);
#define carg(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*гармошкой*\
Комплексное число.

## <a name="return-value"></a>Возвращаемое значение

Аргумент (также известный как фаза) *z*. Результат находится в интервале [-π, + π].

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **Карг** , которые принимают **_Fcomplex** или **_Lcomplex** значения, а также возвращают **`float`** **`long double`** значения или. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **Карг** всегда принимает значение **_Dcomplex** и возвращает **`double`** значение.

При использовании \<tgmath.h> `carg()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**Карг**, **каргф**, **Каргл**|\<complex.h>|\<ccomplex>|
|макрос **Карг** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
