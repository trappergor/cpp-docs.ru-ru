---
title: cproj, cprojf, cprojl
description: Справочник по API для кпрож, кпрожф и кпрожл; который получает проекцию комплексного числа в сфере сферу Римана.
ms.date: 9/2/2020
api_name:
- cproj
- cprojf
- cprojl
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
- cproj
- cprojf
- cprojl
- complex/cproj
- complex/cprojf
- complex/cprojl
helpviewer_keywords:
- cproj function
- cprojf function
- cprojl function
ms.assetid: 32b49623-13bf-4cae-802e-7912d75030fe
ms.openlocfilehash: fcc3c0a42c8c6392130ad58ed12c4985e7ad4907
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555947"
---
# <a name="cproj-cprojf-cprojl"></a>cproj, cprojf, cprojl

Извлекает проекцию комплексного числа на сферу Римана.

## <a name="syntax"></a>Синтаксис

```C
_Dcomplex cproj(
   _Dcomplex z
);
_Fcomplex cproj(
   _Fcomplex z
);  // C++ only
_Lcomplex cproj(
   _Lcomplex z
);  // C++ only
_Fcomplex cprojf(
   _Fcomplex z
);
_Lcomplex cprojl(
   _Lcomplex z
);
#define cproj(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*гармошкой*\
Комплексное число.

## <a name="return-value"></a>Возвращаемое значение

Проекция *z* в сферу Римана Sphere.

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **кпрож** , которые принимают и возвращают **_Fcomplex** и **_Lcomplex** значения. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **кпрож** всегда принимает и возвращает значение **_Dcomplex** .

При использовании \<tgmath.h> `cproj()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**кпрож**, **кпрожф**, **кпрожл**|\<complex.h>|\<ccomplex>|
|макрос **кпрож** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
