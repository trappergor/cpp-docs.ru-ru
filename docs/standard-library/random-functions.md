---
title: Функции &lt;random&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: c8ee20759e66c7beb295de96b8311df46555ac6b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852820"
---
# <a name="ltrandomgt-functions"></a>Функции &lt;random&gt;

## <a name="generate_canonical"></a>  generate_canonical

Возвращает значение с плавающей запятой из случайной последовательности.

> [!NOTE]
> В стандарте ISO C++ указано, что эта функция должна возвращать значения в диапазоне [ `0`, `1`). Visual Studio еще не выполняет это требование. Для получения значений в этом диапазоне используйте [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md).

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Параметры

`RealType` Значение с плавающей запятой в целочисленный тип. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

`Bits` Генератор случайных чисел.

`Gen` Генератор случайных чисел.

### <a name="remarks"></a>Примечания

Функция шаблона повторно вызывает `operator()` класса `Gen` и преобразует возвращенные значения в значение с плавающей запятой `x` типа `RealType`, пока в `x` не будет получено указанное число разрядов мантиссы. Это число меньше значения `Bits` (которое не должно быть нулевым) и меньше полного количества разрядов мантиссы в `RealType`. Первый вызов предоставляет младшие разряды. Функция возвращает `x`.

## <a name="see-also"></a>См. также

[\<random>](../standard-library/random.md)<br/>
