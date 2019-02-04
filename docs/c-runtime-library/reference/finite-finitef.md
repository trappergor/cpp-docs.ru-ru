---
title: isfinite, _finite, _finitef
ms.date: 01/31/2019
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
ms.openlocfilehash: 1be5aa204a7db3054a49c2e05a8fd77b12ae8a3d
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702756"
---
# <a name="isfinite-finite-finitef"></a>isfinite, _finite, _finitef

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

`isfinite` Макрос и `_finite` и `_finitef` функции возвращают ненулевое значение, если *x* является либо обычный или subnormal конечное значение. Они возвращают значение 0, если аргумент является бесконечным или NaN. Встроенная функция шаблона C++ `isfinite` ведет себя так же, но возвращает **true** или **false**.

## <a name="remarks"></a>Примечания

`isfinite` представляет собой макрос, если он компилируется как C и встроенная функция шаблона при компиляции как C++. `_finite` И `_finitef` функции, характерные для Майкрософт. Функция `_finitef` доступна только в случае компиляции для платформ x86, ARM или ARM64.

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
