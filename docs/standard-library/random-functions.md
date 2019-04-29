---
title: Функции &lt;random&gt;
ms.date: 11/04/2016
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 80bdb1ca83be5fb390035d7f3b005793a2f03715
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370350"
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

*RealType*<br/>
Тип с плавающей запятой. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

*BITS*<br/>
Генератор случайных чисел.

*Gen*<br/>
Генератор случайных чисел.

### <a name="remarks"></a>Примечания

Эта функция вызывает шаблон `operator()` из *Gen* многократно и преобразует возвращенные значения в значение с плавающей запятой `x` типа *RealType* пока она собрала заданного числа бит мантиссы в `x`. Является наименьшее значение из заданного числа *Bits* (который должно быть нулевым) и полное число разрядов мантиссы в *RealType*. Первый вызов предоставляет младшие разряды. Функция возвращает `x`.

## <a name="see-also"></a>См. также

[\<random>](../standard-library/random.md)<br/>
