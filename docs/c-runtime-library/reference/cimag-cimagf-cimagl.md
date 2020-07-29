---
title: cimag, cimagf, cimagl
ms.date: 11/04/2016
api_name:
- cimag
- cimagf
- cimagl
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
- cimagf
- cimagl
- complex/cimag
- complex/cimagf
- complex/cimagl
- cimag
helpviewer_keywords:
- cimag function
- cimagf function
- cimagl function
ms.assetid: 0d8836f5-d61d-44cd-8731-6f75cb776def
ms.openlocfilehash: af7d15ee1b5dfd863025565bf8827199f7492841
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232551"
---
# <a name="cimag-cimagf-cimagl"></a>cimag, cimagf, cimagl

Извлекает мнимую часть комплексного числа.

## <a name="syntax"></a>Синтаксис

```C
double cimag( _Dcomplex z );
float cimagf( _Fcomplex z );
long double cimagl( _Lcomplex z );
```

```cpp
float cimag( _Fcomplex z );  // C++
long double cimag( _Lcomplex z );  // C++
```

### <a name="parameters"></a>Параметры

*гармошкой*<br/>
Комплексное число.

## <a name="return-value"></a>Возвращаемое значение

Мнимая часть *z*.

## <a name="remarks"></a>Remarks

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **Цимаг** , которые принимают **_Fcomplex** или **_Lcomplex** значения, а также возвращают **`float`** **`long double`** значения или. В программе на языке C **Цимаг** всегда принимает значение **_Dcomplex** и возвращает **`double`** значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**Цимаг**, **Цимагф**, **Цимагл**|\<complex.h>|\<ccomplex>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
