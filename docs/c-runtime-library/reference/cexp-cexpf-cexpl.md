---
title: cexp, cexpf, cexpl
description: Справочник по API для цексп, цекспф и цекспл; который Вычисляет экспоненту комплексного числа по основанию e.
ms.date: 11/04/2016
api_name:
- cexp
- cexpf
- cexpl
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
- cexp
- cexpf
- cexpl
- complex/cepx
- complex/cexpf
- complex/cexpl
helpviewer_keywords:
- cexp function
- cexpl function
- cexpf function
ms.assetid: f27fd5a9-70c7-4957-a7ee-5256d19bd1da
ms.openlocfilehash: 66f7b687e8da12473abef4dbc44831e175956ac0
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555219"
---
# <a name="cexp-cexpf-cexpl"></a>cexp, cexpf, cexpl

Вычисляет экспоненту комплексного числа с основанием e.

## <a name="syntax"></a>Синтаксис

```C
_Dcomplex cexp( _Dcomplex z );
_Fcomplex cexpf( _Fcomplex z );
_Lcomplex cexpl( _Lcomplex z );

_Fcomplex cexp( _Fcomplex z );  // C++ only
_Lcomplex cexp( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Параметры

*гармошкой*\
Комплексное число, представляющее экспоненту.

## <a name="return-value"></a>Возвращаемое значение

Значение **e** , возведенное в степень *z*.

## <a name="remarks"></a>Примечания

Поскольку C++ допускает перегрузку, можно вызывать перегрузки **цексп** , которые принимают и возвращают **_Fcomplex** и **_Lcomplex** значения. В программе на языке C **цексп** всегда принимает и возвращает значение **_Dcomplex** .

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**цексп**, **цекспф**, **цекспл**|\<complex.h>|\<complex.h>|

Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Алфавитный справочник по функциям](crt-alphabetical-function-reference.md)\
[кпов, кповф, кповл](cpow-cpowf-cpowl.md)\
[clog10, clog10f, clog10l](clog10-clog10f-clog10l.md)\
[clog, clogf, clogl](clog-clogf-clogl.md)
