---
title: Перечисления &lt;limits&gt;
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 567e0538f59c40d57f85d652a8919be6e034cf0b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876036"
---
# <a name="ltlimitsgt-enums"></a>Перечисления &lt;limits&gt;

## <a name="float_denorm_style"></a>float_denorm_style

Перечисление описывает различные методы, которые могут быть выбраны реализацией для представления ненормализованного значения с плавающей запятой, если оно мало для представления в качестве нормализованного значения:

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>Возвращаемое значение

Перечисление возвращает:

- `denorm_indeterminate`, если присутствие или отсутствие денормализованных форм невозможно определить во время преобразования.

- `denorm_absent`, если денормализованные формы отсутствуют.

- `denorm_present`, если денормализованные формы существуют.

### <a name="example"></a>Пример

См. раздел [numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm) с примером, в котором можно получить доступ к значениям этого перечисления.

## <a name="float_round_style"></a>float_round_style

Перечисление описывает различные методы, которые могут быть выбраны реализацией для округления значения с плавающей запятой до целочисленного.

```cpp
enum float_round_style {
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```

### <a name="return-value"></a>Возвращаемое значение

Перечисление возвращает:

- `round_indeterminate`, если не удается определить метод округления.

- `round_toward_zero`, если округление в сторону нуля.

- `round_to_nearest`, если округление до ближайшего целого числа.

- `round_toward_infinity`, если округление отбрасывается от нуля.

- `round_toward_neg_infinity`, если округление до более отрицательного целого числа.

### <a name="example"></a>Пример

См. раздел [numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style) с примером, в котором можно получить доступ к значениям этого перечисления.
