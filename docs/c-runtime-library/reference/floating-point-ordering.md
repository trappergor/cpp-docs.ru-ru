---
title: isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered
ms.date: 01/31/2019
f1_keywords:
- isgreater
- math/isgreater
- isgreaterequal
- math/isgreaterequal
- isless
- math/isless
- islessequal
- math/islessequal
- islessgreater
- math/islessgreater
- isunordered
- math/isunordered
helpviewer_keywords:
- isgreater function
- isgreaterequal function
- isless function
- islessequal function
- islessgreater function
- isunordered function
ms.openlocfilehash: 748360cae1dd0ee43645dee369c60c835246ed03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333707"
---
# <a name="isgreater-isgreaterequal-isless-islessequal-islessgreater-isunordered"></a>isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered

Определяет упорядочивания связь между двумя значениями с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
int isgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isgreaterequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isless(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isunordered(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */
```

```C++
template <class FloatingType1, class FloatingType2>
inline bool isgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isgreaterequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isless(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isunordered(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>Параметры

*x*, *y*<br/>
Значения с плавающей запятой для сравнения.

## <a name="return-value"></a>Возвращаемое значение

При всех сравнениях бесконечности с тем же знаком сравнении считаются равными. Отрицательная бесконечность — меньше, чем любой конечное значение или положительной бесконечности. Положительная бесконечность больше, чем любое конечное значение или минус бесконечности. Нулевые значения считаются равными, независимо от входа. Значения NaN не меньшим, равным или больше, чем любое значение, в том числе другой NaN.

Когда ни один из аргументов имеет значение NaN, упорядочивания макросы **isgreater**, **isgreaterequal**, **isless**, и **islessequal** возвращают ненулевое значение значение, если указанное отношение упорядочивания между *x* и *y* содержит значение true. Эти макросы возвращают 0, если один или оба аргумента имеют значения NaN, или если упорядочивания связи имеет значение false. Forms функции ведут себя одинаково, но возвращает **true** или **false**.

**Islessgreater** макрос возвращает ненулевое значение, если оба *x* и *y* не являются значения NaN, и *x* либо меньше или больше, чем *y*. Она возвращает 0, если один или оба аргумента имеют значения NaN, или если значения равны. Форма функция ведет себя так же, но возвращает **true** или **false**.

**Isunordered** макрос возвращает ненулевое значение, если *x*, *y*, или оба имеют значения NaN. В противном случае она возвращает 0. Форма функция ведет себя так же, но возвращает **true** или **false**.

## <a name="remarks"></a>Примечания

Эти операции сравнения, реализуются как макросы, при компиляции как C и как встраиваемые функции шаблона, при компиляции как C++.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок (C)|Обязательный заголовок (C++)|
|--------------|---------------------------|-------------------------------|
| **isgreater**, **isgreaterequal**, **isless**,<br/>**islessequal**, **islessgreater**, **isunordered** | \<math.h> | \<math.h> или \<cmath> |

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
