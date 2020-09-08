---
title: ctanh, ctanhf, ctanhl
description: Справочник по API для ктанх, ктанхф, ктанхл; который рассчитывает Комплексный гиперболический тангенс комплексного числа.
ms.date: 11/04/2016
api_name:
- ctanh
- ctanhf
- ctanhl
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
- ctanh
- ctanhf
- ctanhl
- complex/ctanh
- complex/ctanhf
- complex/ctanhl
helpviewer_keywords:
- ctanh function
- ctanhl function
- ctanhf function
ms.assetid: 807f2cd1-8740-4988-afff-5911c346385b
ms.openlocfilehash: 959d48853e3edac707a7daea615270b20dad37e7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555870"
---
# <a name="ctanh-ctanhf-ctanhl"></a>ctanh, ctanhf, ctanhl

Вычисляет комплексный гиперболический тангенс комплексного числа.

## <a name="syntax"></a>Синтаксис

```C
_Dcomplex ctanh(
   _Dcomplex z
);
_Fcomplex ctanh(
   _Fcomplex z
);  // C++ only
_Lcomplex ctanh(
   _Lcomplex z
);  // C++ only
_Fcomplex ctanhf(
   _Fcomplex z
);
_Lcomplex ctanhl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Параметры

*гармошкой*\
Комплексное число, указывающее угол в радианах.

## <a name="return-value"></a>Возвращаемое значение

Сложный гиперболический тангенс *z*.

|Входные данные|Исключение SEH|**_matherr** Об|
|-----------|-------------------|--------------------------|
|± ∞, КНАН, ТО ЕСТЬ|нет|_DOMAIN|
|± ∞ (Tan, TANF)|INVALID|_DOMAIN|

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **ктанх** , которые принимают и возвращают **_Fcomplex** и **_Lcomplex** значения. В программе на языке C **ктанх** всегда принимает и возвращает значение **_Dcomplex** .

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**ктанх**,               **ктанхф**, **ктанхл**|\<complex.h>|\<ccomplex>|

Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[catan, catanf, catanl](catan-catanf-catanl.md)<br/>
[csinh, csinhf, csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh, ccoshf, ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh, cacoshf, cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos, cacosf, cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[casin, casinf, casinl](casin-casinf-casinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>
