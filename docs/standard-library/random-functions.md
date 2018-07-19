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
ms.openlocfilehash: 5b0cd634dad099669d803d4a2717fc9198151781
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954162"
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

*RealType* целочисленный тип с плавающей запятой. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

*Биты* генератора случайных чисел.

*Gen* генератора случайных чисел.

### <a name="remarks"></a>Примечания

Эта функция вызывает шаблон `operator()` из *Gen* многократно и преобразует возвращенные значения в значение с плавающей запятой `x` типа *RealType* пока она собрала заданного числа бит мантиссы в `x`. Является наименьшее значение из заданного числа *Bits* (который должно быть нулевым) и полное число разрядов мантиссы в *RealType*. Первый вызов предоставляет младшие разряды. Функция возвращает `x`.

## <a name="see-also"></a>См. также

[\<random>](../standard-library/random.md)<br/>
