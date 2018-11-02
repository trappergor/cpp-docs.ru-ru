---
title: _Cbuild, _FCbuild, _LCbuild
ms.date: 03/30/2018
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
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
ms.openlocfilehash: 5565c87a3cccd1715a1357f417238587f3fba4d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511804"
---
# <a name="cbuild-fcbuild-lcbuild"></a>_Cbuild, _FCbuild, _LCbuild

Создает комплексное число из вещественной и мнимой частей.

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

Объект **_Dcomplex**, **_Fcomplex**, или **_Lcomplex** структуру, которая представляет комплексное число (*реальных*, *мнимой*  \* я) для значений указанного типа с плавающей запятой.

## <a name="remarks"></a>Примечания

**_Cbuild**, **_FCbuild**, и **_LCbuild** функции упрощают создание сложных типов. Используйте [creal, crealf, creall](creal-crealf-creall.md) и [cimag, cimagf, cimagl](cimag-cimagf-cimagl.md) функции извлечения и действительная и мнимая части представлен комплексных чисел.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**_Cbuild**, **_FCbuild**, **_LCbuild**|\<complex.h>|\<ccomplex>|

Эти функции зависят от Microsoft. Типы **_Dcomplex**, **_Fcomplex**, и **_Lcomplex** характерные для Майкрософт эквивалентов в Нереализованная собственные типы C99 **double _Complex** , **float _Complex**, и **long double _Complex**, соответственно. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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
