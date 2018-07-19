---
title: _Cmulcr _FCmulcr, _LCmulcr | Документы Microsoft
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- _Cmulcr
- _FCmulcr
- _LCmulcr
apilocation:
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
apitype: DLLExport
f1_keywords:
- _Cmulcr
- _FCmulcr
- _LCmulcr
- complex/_Cmulcr
- complex/_FCmulcr
- complex/_LCmulcr
dev_langs:
- C++
helpviewer_keywords:
- _Cmulcr function
- _FCmulcr function
- _LCmulcr function
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbd42e4c543d4bc42afa023d62b328a143c90374
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395029"
---
# <a name="cmulcr-fcmulcr-lcmulcr"></a>_Cmulcr _FCmulcr, _LCmulcr

Умножает комплексное число, число с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
_Dcomplex _Cmulcr( _Dcomplex x, double y );
_Fcomplex _FCmulcr( _Fcomplex x, float y );
_Lcomplex _LCmulcr( _Lcomplex x, long double y );
```

### <a name="parameters"></a>Параметры

*x*<br/>
Один из операндов сложный для умножения.

*y*<br/>
Операнд для умножения чисел с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Объект **_Dcomplex**, **_Fcomplex**, или **_Lcomplex** структуру, которая представляет сложный продукт комплексного числа *x* и номер точки flaoting *y*.

## <a name="remarks"></a>Примечания

Так как встроенные арифметические операторы работают в реализации корпорацией Майкрософт, сложные типы **_Cmulcr**, **_FCmulcr**, и **_LCmulcr** функции Упростите умножения сложных типов, типов с плавающей запятой.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**_Cmulcr**, **_FCmulcr**, **_LCmulcr**|\<complex.h>|\<complex.h>|

Эти функции зависят от корпорации Майкрософт. Типы **_Dcomplex**, **_Fcomplex**, и **_Lcomplex** , характерные для Майкрософт эквиваленты нереализованные C99 собственные типы **двойные _Complex** , **float _Complex**, и **long double _Complex**соответственно. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
