---
title: _Cmulcc, _FCmulcc, _LCmulcc
ms.date: 03/30/2018
api_name:
- _Cmulcc
- _FCmulcc
- _LCmulcc
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
- _Cmulcc
- _FCmulcc
- _LCmulcc
- complex/_Cmulcc
- complex/_FCmulcc
- complex/_LCmulcc
helpviewer_keywords:
- _Cmulcc function
- _FCmulcc function
- _LCmulcc function
ms.openlocfilehash: fc21f8cbd2103993bc2b3e36020c57c8520f04a1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939075"
---
# <a name="_cmulcc-_fcmulcc-_lcmulcc"></a>_Cmulcc, _FCmulcc, _LCmulcc

Умножает два комплексных числа.

## <a name="syntax"></a>Синтаксис

```C
_Dcomplex _Cmulcc( _Dcomplex x, _Dcomplex y );
_Fcomplex _FCmulcc( _Fcomplex x, _Fcomplex y );
_Lcomplex _LCmulcc( _Lcomplex x, _Lcomplex y );
```

### <a name="parameters"></a>Параметры

*x*<br/>
Один из сложных операндов для умножения.

*y*<br/>
Другой сложный операнд для умножения.

## <a name="return-value"></a>Возвращаемое значение

Структура **_Dcomplex**, **_Fcomplex**или **_Lcomplex** , представляющая комплексное произведение комплексных чисел *x* и *y*.

## <a name="remarks"></a>Примечания

Поскольку встроенные арифметические операторы не работают в реализации сложных типов в Майкрософт, функции **_Cmulcc**, **_FCmulcc**и **_LCmulcc** упрощают умножение сложных типов.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**_Cmulcc**, **_FCmulcc**, **_LCmulcc**|\<complex.h>|\<complex.h>|

Эти функции относятся только к Microsoft. Типы **_Dcomplex**, **_Fcomplex**и **_Lcomplex** являются эквивалентами, специфичными для Microsoft, для нереализованных C99 машинных типов **Double _Complex**, **float _Complex**и **long double _Complex**соответственно. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
