---
title: Перечисления &lt;limits&gt;
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 68f0ba605b62f2492f49a2b81030c42dca80bf5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653288"
---
# <a name="ltlimitsgt-enums"></a>Перечисления &lt;limits&gt;

|||
|-|-|
|[float_denorm_style](#float_denorm_style)|[float_round_style](#float_round_style)|

## <a name="float_denorm_style"></a>  Перечисление float_denorm_style

Перечисление описывает различные методы, которые могут быть выбраны реализацией для представления ненормализованного значения с плавающей запятой, если оно мало для представления в качестве нормализованного значения:

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>Возвращаемое значение

Перечисление возвращает:

- `denorm_indeterminate` Если не удается определить наличие или отсутствие денормализованных форм во время преобразования.

- `denorm_absent` Если денормализованные формы отсутствуют.

- `denorm_present` Если денормализованные формы присутствуют.

### <a name="example"></a>Пример

См. раздел [numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm) с примером, в котором можно получить доступ к значениям этого перечисления.

## <a name="float_round_style"></a>  Перечисление float_round_style

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

- `round_indeterminate` Если метод округления невозможно определить.

- `round_toward_zero` Если округление к нулю.

- `round_to_nearest` Если округление до ближайшего целого числа.

- `round_toward_infinity` Если округление от ноля.

- `round_toward_neg_infinity` Если округление к более отрицательному целому.

### <a name="example"></a>Пример

См. раздел [numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style) с примером, в котором можно получить доступ к значениям этого перечисления.

## <a name="see-also"></a>См. также

[\<limits>](../standard-library/limits.md)<br/>
