---
title: _scalb _scalbf
ms.date: 04/05/2018
apiname:
- _scalb
- _scalbf
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
- scalb
- _scalb
- _scalbf
helpviewer_keywords:
- exponential calculations
- _scalb function
- _scalbf function
- scalb function
ms.assetid: 148cf5a8-b405-44bf-a1f0-7487adba2421
ms.openlocfilehash: c3f776ec27c365601d4fe57fb6cf0a5c9b9e0cbd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551038"
---
# <a name="scalb-scalbf"></a>_scalb _scalbf

Масштабирует аргумент по степени числа 2.

## <a name="syntax"></a>Синтаксис

```C
double _scalb(
   double x,
   long exp
);
float _scalbf(
   float x,
   long exp
); /* x64 only */
```

### <a name="parameters"></a>Параметры

*x*<br/>
Число двойной точности с плавающей запятой.

*exp*<br/>
Показатель степени — длинное целое число.

## <a name="return-value"></a>Возвращаемое значение

Возвращает значение экспоненты в случае успешного выполнения. При переполнении (в зависимости от знака *x*), **_scalb** возвращает +/- **HUGE_VAL**; **errno** переменной присваивается  **ERANGE**.

Дополнительные сведения об этом и других кодах возврата см. в статье [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Scalb** функция вычисляет значение *x* \* 2<sup>*exp*</sup>.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_scalb**, **_scalbf**|\<float.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
