---
title: _Cbuild, _FCbuild, _LCbuild
ms.date: 03/30/2018
api_name:
- _Cbuild
- _FCbuild
- _LCbuild
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
- _Cbuild
- _FCbuild
- _LCbuild
- complex/_Cbuild
- complex/_FCbuild
- complex/_LCbuild
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
ms.openlocfilehash: b0ae50f40f0ca0a926e1eef586c6610a04b6ea7a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943217"
---
# <a name="_cbuild-_fcbuild-_lcbuild"></a>_Cbuild, _FCbuild, _LCbuild

Конструирует комплексное число от реальных и мнимых частей.

## <a name="syntax"></a>Синтаксис

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>Параметры

*real*<br/>
Вещественная часть комплексного числа для создания.

*мнимой*<br/>
Мнимая часть комплексного числа для создания.

## <a name="return-value"></a>Возвращаемое значение

Структура **_Dcomplex**, **_Fcomplex**или **_Lcomplex** , представляющая комплексное число \* (*вещественное*, *мнимое* i) для значений указанного типа с плавающей запятой.

## <a name="remarks"></a>Примечания

Функции **_Cbuild**, **_FCbuild**и **_LCbuild** упрощают создание сложных типов. Используйте функции [Креал, креалф, креалл](creal-crealf-creall.md) и [Цимаг, Цимагф, Цимагл,](cimag-cimagf-cimagl.md) чтобы получить действительные и мнимые части представленных комплексных чисел.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**_Cbuild**, **_FCbuild**, **_LCbuild**|\<complex.h>|\<ccomplex>|

Эти функции относятся только к Microsoft. Типы **_Dcomplex**, **_Fcomplex**и **_Lcomplex** являются эквивалентами, специфичными для Microsoft, для нереализованных C99 машинных типов **Double _Complex**, **float _Complex**и **long double _Complex**соответственно. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
