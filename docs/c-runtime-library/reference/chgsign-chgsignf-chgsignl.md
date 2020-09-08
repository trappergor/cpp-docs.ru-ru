---
title: _chgsign, _chgsignf, _chgsignl
description: Справочник по API для _chgsign, _chgsignf и _chgsignl; который изменяет знак аргумента с плавающей запятой на противоположный.
ms.date: 04/05/2018
api_name:
- _chgsignl
- _chgsign
- _chgsignf
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
- _chgsignf
- chgsign
- _chgsignl
- _chgsign
helpviewer_keywords:
- _chgsignl function
- _chgsignf function
- chgsign function
- _chgsign function
ms.assetid: a6646f8e-213d-4564-8617-f43bc66f989f
ms.openlocfilehash: 7dc934f3c2d22cc36abe5f31f7d64e0674ccdd3a
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555206"
---
# <a name="_chgsign-_chgsignf-_chgsignl"></a>_chgsign, _chgsignf, _chgsignl

Меняет знак аргумента с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
double _chgsign(
   double x
);
float _chgsignf(
   float x
);
long double _chgsignl(
   long double x
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой, которое необходимо изменить.

## <a name="return-value"></a>Возвращаемое значение

Функции **_chgsign** возвращают значение, равное аргументу *x*с плавающей запятой, но с обратным знаком. Ошибки не возвращаются.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_chgsign**|\<float.h>|
|**_chgsignf**, **_chgsignl**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Дополнительно

[Поддержка операций с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl](copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)<br/>
