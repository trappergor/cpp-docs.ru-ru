---
title: Класс subtract_with_carry_engine | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::subtract_with_carry_engine
- random/std::subtract_with_carry_engine::default_seed
- random/std::subtract_with_carry_engine::discard
- random/std::subtract_with_carry_engine::min
- random/std::subtract_with_carry_engine::max
- random/std::subtract_with_carry_engine::seed
dev_langs:
- C++
helpviewer_keywords:
- std::subtract_with_carry_engine [C++]
- std::subtract_with_carry_engine [C++], default_seed
- std::subtract_with_carry_engine [C++], discard
- std::subtract_with_carry_engine [C++], min
- std::subtract_with_carry_engine [C++], max
- std::subtract_with_carry_engine [C++], seed
ms.assetid: 94a055f2-a620-4a22-ac34-c156924bab31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfb0c3c0544a9c58801f98567825e7e97e48b13c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687991"
---
# <a name="subtractwithcarryengine-class"></a>Класс subtract_with_carry_engine

Создает случайную последовательность, используя алгоритм вычитания с переносом (метод Фибоначчи с запаздываниями).

## <a name="syntax"></a>Синтаксис

```cpp
template <class UIntType, size_t W, size_t S, size_t R>
class subtract_with_carry_engine;
```

### <a name="parameters"></a>Параметры

*UIntType*  
 Беззнаковый целочисленный тип результата. Возможные типы см. в разделе [\<random>](../standard-library/random.md).

*W*  
 **Размер слова**. Размер каждого слова последовательности состояния в битах. **Предварительные условия**: `0 < W ≤ numeric_limits<UIntType>::digits`

*S*  
 **Короткая задержка**. Количество целочисленных значений. **Предварительные условия**: `0 < S < R`

*R*  
 **Длинная задержка**. Определяет повторения в созданном ряду.

## <a name="members"></a>Члены

||||
|-|-|-|
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|
|`default_seed` — это член-константа, определенный как `19780503u` и используемый как значение по умолчанию для параметра `subtract_with_carry_engine::seed` и конструктор с одним значением.|||

Дополнительные сведения о членах механизма см. в разделе [\<random>](../standard-library/random.md).

## <a name="remarks"></a>Примечания

Класс шаблона `substract_with_carry_engine` — это улучшение [linear_congruential_engine](../standard-library/linear-congruential-engine-class.md). Ни один из этих механизмов не обеспечивает такую же скорость и качество результатов, как механизм [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md).

Этот механизм формирует значения указанного пользователем беззнакового целого типа, используя рекуррентное соотношение (*период*) `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M`, где `cy(i)` имеет значение `1`, если `x(i - S) - x(i - R) - cy(i - 1) < 0`; в противном случае — значение `0`, а `M` имеет значение `2`<sup>W</sup>. Состояние механизма — это перенос индикатор плюс *R* значения. Эти значения состоят из последнего *R* возвращается, если значения `operator()` был вызван хотя бы *R* время ожидания, в противном случае `N` значения, которые были возвращены, а последний `R - N` значения начального значения.

Аргумент шаблона `UIntType` должен быть достаточно большим, чтобы хранить значения до `M - 1`.

Хотя можно создать генератор на основе этого механизма напрямую, также можно использовать одно из этих предварительно заданных определений типов:

`ranlux24_base`: используется в качестве основания для `ranlux24`.
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`

`ranlux48_base`: используется в качестве основания для `ranlux48`.
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`

Дополнительные сведения об алгоритме вычитания с переносом см. в статье [Генератор Фибоначчи с запаздываниями](https://en.wikipedia.org/wiki/Lagged_Fibonacci_generator) на веб-сайте Википедии.

## <a name="requirements"></a>Требования

**Заголовок:** \<random>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<random>](../standard-library/random.md)<br/>
