---
title: _Cbuild _FCbuild, _LCbuild | Документы Microsoft
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- _Cbuild
- _FCbuild
- _LCbuild
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
- _Cbuild
- _FCbuild
- _LCbuild
- complex/_Cbuild
- complex/_FCbuild
- complex/_LCbuild
dev_langs:
- C++
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6d567dc02715b9e55644b755b6d7360f2fe3d37
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394391"
---
# <a name="cbuild-fcbuild-lcbuild"></a>_Cbuild _FCbuild, _LCbuild

Строит комплексное число из вещественной и мнимой частей.

## <a name="syntax"></a>Синтаксис

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>Параметры

*real*<br/>
Действительная часть комплексного числа, для построения.

*мнимая*<br/>
Мнимая часть комплексного числа, для построения.

## <a name="return-value"></a>Возвращаемое значение

Объект **_Dcomplex**, **_Fcomplex**, или **_Lcomplex** структуру, которая представляет комплексное число (*реальные*, *мнимой*  \* я) для значения заданного типа с плавающей запятой.

## <a name="remarks"></a>Примечания

**_Cbuild**, **_FCbuild**, и **_LCbuild** функции упрощают создание сложных типов. Используйте [creal crealf, creall](creal-crealf-creall.md) и [cimag cimagf, cimagl](cimag-cimagf-cimagl.md) функции для получения действительной и мнимой частей представленном комплексных чисел.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**_Cbuild**, **_FCbuild**, **_LCbuild**|\<complex.h>|\<ccomplex>|

Эти функции зависят от корпорации Майкрософт. Типы **_Dcomplex**, **_Fcomplex**, и **_Lcomplex** , характерные для Майкрософт эквиваленты нереализованные C99 собственные типы **двойные _Complex** , **float _Complex**, и **long double _Complex**соответственно. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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
