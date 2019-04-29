---
title: copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl
ms.date: 04/05/2018
apiname:
- copysignf
- copysignl
- _copysignl
- _copysign
- _copysignf
- copysign
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
- _copysignl
- copysign
- copysignf
- _copysign
- copysignl
- _copysignf
helpviewer_keywords:
- copysignl function
- _copysignl function
- copysign function
- _copysignf function
- _copysign function
- copysignf function
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
ms.openlocfilehash: 6f450da4a4391f94d1905beefdeca8e3f01fec51
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349060"
---
# <a name="copysign-copysignf-copysignl-copysign-copysignf-copysignl"></a>copysign, copysignf, copysignl, _copysign, _copysignf, _copysignl

Возвращает значение, которое имеет абсолютное значение одного аргумента и знак другого.

## <a name="syntax"></a>Синтаксис

```C
double copysign(
   double x,
   double y
);
float copysign(
   float x,
   float y
); // C++ only
long double copysign(
   long double x,
   long double y
); // C++ only
float copysignf(
   float x,
   float y
); // C++ only
long double copysignl(
   long double x,
   long double y
); // C++ only
double _copysign(
   double x,
   double y
);
long double _copysignl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Значение с плавающей запятой, которое возвращается как абсолютное значение результата.

*y*<br/>
Значение с плавающей запятой, которое возвращается как знак результата.

[Подпрограммы поддержки чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)

## <a name="return-value"></a>Возвращаемое значение

**Copysign** функции возвращают значение с плавающей запятой, которое объединяет абсолютное значение *x* и знак *y*. Ошибка не возвращается.

## <a name="remarks"></a>Примечания

Так как C++ допускает перегрузку, можно вызывать перегрузки **copysign** , принимающие и возвращающие **float** или **long** **двойные** значения. В программе на языке C **copysign** всегда принимает и возвращает **двойные**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_copysign**|\<float.h>|
|**copysign**, **copysignf**, **copysignl**, **_copysignf**, **_copysignl**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[_chgsign, _chgsignf, _chgsignl](chgsign-chgsignf-chgsignl.md)<br/>
