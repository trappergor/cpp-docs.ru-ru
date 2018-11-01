---
title: norm, normf, norml
ms.date: 04/05/2018
apiname:
- norm
- normf
- norml
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
- norm
- normf
- norml
- complex/norm
- complex/normf
- complex/norml
helpviewer_keywords:
- norm function
- normf function
- norml function
ms.assetid: 9786ecfe-0019-4553-b378-0af6c691e15c
ms.openlocfilehash: 3c1803a54f0dfc27975af5bb0eeb7e5c042b2579
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628115"
---
# <a name="norm-normf-norml"></a>norm, normf, norml

Возвращает абсолютное значение комплексного числа в квадрате.

## <a name="syntax"></a>Синтаксис

```C
double norm( _Dcomplex z );
float normf( _Fcomplex z );
long double norml( _Lcomplex z );
```

```cpp
float norm( _Fcomplex z );  // C++ only
long double norm( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Параметры

*z*<br/>
Комплексное число.

## <a name="return-value"></a>Возвращаемое значение

Абсолютное значение в квадрате из *z*.

## <a name="remarks"></a>Примечания

Так как C++ допускает перегрузку, можно вызывать перегрузки **norm** , принимающих **_Fcomplex** или **_Lcomplex** и возвращают **float** или **long double** значения. В программе на языке C **norm** всегда принимает **_Dcomplex** значения и возвращает **двойные** значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**Норма**, **normf**, **norml**|\<complex.h>|\<complex.h>|

**_Fcomplex**, **_Dcomplex**, и **_Lcomplex** типы являются эквивалентами характерные для Майкрософт Нереализованная собственные типы C99 **float _Complex** , **double _Complex**, и **long double _Complex**, соответственно.  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
