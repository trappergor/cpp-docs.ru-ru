---
title: Перечисления &lt;limits&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: ca3117cc3b84fb4f143dfaa45471d4d2ebd55663
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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

- **denorm_indeterminate**, если не удается определить наличие или отсутствие денормализованных форм во время преобразования.

- **denorm_absent**, если денормализованные формы отсутствуют.

- **denorm_present**, если денормализованные формы присутствуют.

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

- **round_indeterminate**, если метод округления определить не удается.

- **round_toward_zero**, если округление к нолю.

- **round_to_nearest**, если округление до ближайшего целого числа.

- **round_toward_infinity**, если округление от ноля.

- **round_toward_neg_infinity**, если округление к более отрицательному целому числу.

### <a name="example"></a>Пример

См. раздел [numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style) с примером, в котором можно получить доступ к значениям этого перечисления.

## <a name="see-also"></a>См. также

[\<limits>](../standard-library/limits.md)<br/>
