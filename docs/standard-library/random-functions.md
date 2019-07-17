---
title: Функции &lt;random&gt;
ms.date: 11/04/2016
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 87b640d4f3aa3fbfa23ad5603d84102301e71ea4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240390"
---
# <a name="ltrandomgt-functions"></a>Функции &lt;random&gt;

## <a name="generate_canonical"></a> generate_canonical

Возвращает значение с плавающей запятой из случайной последовательности.

> [!NOTE]
> В стандарте ISO C++ указано, что эта функция должна возвращать значения в диапазоне [ `0`, `1`). Visual Studio еще не выполняет это требование. Для получения значений в этом диапазоне используйте [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md).

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Параметры

*RealType*\
Тип с плавающей запятой. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

*BITS*\
Генератор случайных чисел.

*Gen*\
Генератор случайных чисел.

### <a name="remarks"></a>Примечания

Эта функция вызывает шаблон `operator()` из *Gen* многократно и преобразует возвращенные значения в значение с плавающей запятой `x` типа *RealType* пока она собрала заданного числа бит мантиссы в `x`. Является наименьшее значение из заданного числа *Bits* (который должно быть нулевым) и полное число разрядов мантиссы в *RealType*. Первый вызов предоставляет младшие разряды. Функция возвращает `x`.
