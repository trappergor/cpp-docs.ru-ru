---
title: creal, crealf, creall | Документы Майкрософт
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- creal
- crealf
- creall
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
- creal
- crealf
- creall
- complex/creal
- complex/crealf
- complex/creall
dev_langs:
- C++
helpviewer_keywords:
- creal function
- crealf function
- creall function
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc43c72c4fcbaf9d24c1a2c4cc7b7923d0c67878
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2018
---
# <a name="creal-crealf-creall"></a>creal, crealf, creall

Извлекает реальную часть комплексного числа.

## <a name="syntax"></a>Синтаксис

```C
double creal( _Dcomplex z );
float crealf( _Fcomplex z );
long double creall( _Lcomplex z );
```

```cpp
float creal( _Fcomplex z );  // C++ only
long double creal( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Параметры

*z*<br/>
Комплексное число.

## <a name="return-value"></a>Возвращаемое значение

Действительная часть *z*.

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки `creal` , которые принимают **_Fcomplex** или **_Lcomplex** значений и возвращают **float** или **long двойные** значения. В программе на языке C `creal` всегда принимает **_Dcomplex** значения и возвращает **двойные** значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|`creal`, `crealf`, `creall`|\<complex.h>|\<ccomplex>|

**_Fcomplex**, **_Dcomplex**, и **_Lcomplex** типы являются эквивалентами характерные для Майкрософт нереализованные собственных типов C99 **float _Complex** , **двойные _Complex**, и **long double _Complex**соответственно. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](../../c-runtime-library/reference/cbuild-fcbuild-lcbuild.md)<br/>
[norm, normf, norml](../../c-runtime-library/reference/norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](../../c-runtime-library/reference/cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](../../c-runtime-library/reference/conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](../../c-runtime-library/reference/cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](../../c-runtime-library/reference/carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](../../c-runtime-library/reference/cabs-cabsf-cabsl.md)<br/>