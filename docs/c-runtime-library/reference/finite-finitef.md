---
title: _finite, _finitef
ms.date: 04/05/2018
apiname:
- _finite
- _finitef
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
- finite
- _finite
- _finitef
- math/_finite
- math/_finitef
- float/_finite
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
ms.openlocfilehash: 7b1bce6f1b2da77ed9de255f49dd8d0160e33e31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431681"
---
# <a name="finite-finitef"></a>_finite, _finitef

Определяет, является ли значение с плавающей запятой конечным.

## <a name="syntax"></a>Синтаксис

```C
int _finite(
   double x
);

int _finitef(
   float x
); /* x64 and ARM/ARM64 only */
```

### <a name="parameters"></a>Параметры

*x*<br/>
Проверяемое значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

Оба **_finite** и **_finitef** возвращают ненулевое значение, если аргумент *x* является конечным, то есть, если -INF < *x* < + INF. Возвращает 0, если аргумент является бесконечным или NAN.

## <a name="remarks"></a>Примечания

**_Finite** и **_finitef** функции только к системам Майкрософт. **_Finitef** функции находятся только доступно, если для x86, ARM или ARM64 платформ.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|--------------|---------------------------|-------------------------------|
|**_finite**|\<float.h> или \<math.h>|\<float.h>, \<math.h>, \<cfloat> или \<cmath>|
|**_finitef**|\<math.h>|\<math.h> или \<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
