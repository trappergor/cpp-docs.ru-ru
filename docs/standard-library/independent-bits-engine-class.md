---
title: Класс independent_bits_engine
ms.date: 11/04/2016
f1_keywords:
- random/std::independent_bits_engine
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
ms.openlocfilehash: a90e4be4ff6e92734f6b2e6804f8059be78e66b9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456346"
---
# <a name="independentbitsengine-class"></a>Класс independent_bits_engine

Создает случайную последовательность чисел с указанным числом разрядов, перемешивая разряды из значений, возвращенных базовым механизмом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>Параметры

*Ядре*\
Тип базового механизма.

*БЕЛАЯ*\
**Размер слова**. Размер каждого полученного числа в битах. **Предварительные условия**: `0 < W ≤ numeric_limits<UIntType>::digits`

*уинттипе*\
Беззнаковый целочисленный тип результата. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

## <a name="members"></a>Участники

||||
|-|-|-|
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|

Дополнительные сведения о членах механизма см. в разделе [\<random>](../standard-library/random.md).

## <a name="remarks"></a>Примечания

Этот класс шаблона описывает *адаптер подсистемы* , создающий значения путем повторного упаковки битов из значений, возвращенных базовым механизмом, в результате чего используются значения *W*bit.

## <a name="requirements"></a>Требования

**Заголовок:** \<random>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<random>](../standard-library/random.md)
