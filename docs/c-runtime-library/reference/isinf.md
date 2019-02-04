---
title: isinf
ms.date: 01/31/2019
f1_keywords:
- isinf
- math/isinf
helpviewer_keywords:
- isinf function
ms.openlocfilehash: be99970a0c7b152ba213eabd59b53a7503cd3c54
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703472"
---
# <a name="isinf"></a>isinf

Определяет, является ли значение с плавающей запятой бесконечности.

## <a name="syntax"></a>Синтаксис

```C
int isinf(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isinf(
   FloatingType x
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>Параметры

*x*<br/>
Проверяемое значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

**isinf** возвращает ненулевое значение (**true** в коде C++) Если аргумент *x* является положительная или отрицательная бесконечность. **isinf** возвращает 0 (**false** в коде C++), если аргумент является конечным или NAN. Нормальные и subnormal значения с плавающей запятой, считаются конечным.

## <a name="remarks"></a>Примечания

**isinf** представляет собой макрос, если он компилируется как C и встроенная функция шаблона при компиляции как C++.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|--------------|---------------------------|-------------------------------|
|**isinf**|\<math.h>|\<math.h> или \<cmath>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
