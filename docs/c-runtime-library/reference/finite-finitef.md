---
title: isfinite, _finite, _finitef
ms.date: 01/31/2019
api_name:
- _finite
- _finitef
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- isfinite
- finite
- _finite
- _finitef
- math/isfinite
- math/_finite
- math/_finitef
- float/_finite
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
ms.openlocfilehash: a2cde4d3a57884413f0c48aa299b171334c5f988
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957180"
---
# <a name="isfinite-_finite-_finitef"></a>isfinite, _finite, _finitef

Определяет, является ли значение с плавающей запятой конечным.

## <a name="syntax"></a>Синтаксис

```C
int isfinite(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isfinite(
   FloatingType x
) throw(); /* C++-only template function */

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

Макросы и функции `_finitef` и возвращают ненулевое значение, если x является нормальным или поднормальным конечным значением. `_finite` `isfinite` Они возвращают 0, если аргумент имеет бесконечное значение или NaN. C++ `isfinite` Встроенная функция шаблона ведет себя таким же образом, но возвращает **значение true** или **false**.

## <a name="remarks"></a>Примечания

`isfinite`макрос при компиляции в виде C и встроенная функция шаблона при компиляции как C++. Функции `_finite` и`_finitef` являются специфичными для Microsoft. Функция `_finitef` доступна только в случае компиляции для платформ x86, ARM или ARM64.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|--------------|---------------------------|-------------------------------|
|`_finite`|\<float.h> или \<math.h>|\<float.h>, \<math.h>, \<cfloat> или \<cmath>|
|`isfinite`, `_finitef`|\<math.h>|\<math.h> или \<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
