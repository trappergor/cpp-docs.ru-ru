---
title: conj, conjf, conjl
description: Справочник по API для конж, конжф и конжл; для получения комплексного сопряженного комплексного числа.
ms.date: 9/2/2020
api_name:
- conj
- conjf
- conjl
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
- conj
- conjf
- conjl
- complex/conj
- complex/conjf
- complex/conjl
helpviewer_keywords:
- conj function
- conjf function
- conjl function
ms.assetid: 792fccfa-19c6-4890-99f9-a3b89effccd6
ms.openlocfilehash: b779eb2d92893b204a73b2fa4f5c89928933ffeb
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556357"
---
# <a name="conj-conjf-conjl"></a>conj, conjf, conjl

Извлекает комплексно-сопряженную величину комплексного числа.

## <a name="syntax"></a>Синтаксис

```C
_Dcomplex conj(
   _Dcomplex z
);
_Fcomplex conj(
   _Fcomplex z
);  // C++ only
_Lcomplex conj(
   _Lcomplex z
);  // C++ only
_Fcomplex conjf(
   _Fcomplex z
);
_Lcomplex conjl(
   _Lcomplex z
);
#define conj(X) // Requires C11 or higher
```

### <a name="parameters"></a>Параметры

*гармошкой*\
Комплексное число.

## <a name="return-value"></a>Возвращаемое значение

Комплексный сопряженный с *z*.  Результат имеет ту же реальную и мнимую часть, что и *z*, но с противоположным знаком.

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **конж** , которые принимают и возвращают **_Fcomplex** и **_Lcomplex** значения. В программе на языке C, если только вы не используете \<tgmath.h> макрос для вызова этой функции, **конж** всегда принимает и возвращает значение **_Dcomplex** .

При использовании \<tgmath.h> `conj()` макроса тип аргумента определяет, какая версия функции выбрана. Подробные сведения см. в разделе [Type-Generic Math](../../c-runtime-library/tgmath.md) .

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**конж**, **конжф**, **конжл**|\<complex.h>|\<ccomplex>|
|макрос **конж** | \<tgmath.h> ||

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
