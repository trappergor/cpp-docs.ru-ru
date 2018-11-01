---
title: Класс discard_block_engine
ms.date: 11/04/2016
f1_keywords:
- random/std::discard_block_engine
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
ms.openlocfilehash: a0df754f53b52c134b9eb1126f90882ceaaf1e2f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676828"
---
# <a name="discardblockengine-class"></a>Класс discard_block_engine

Создает случайную последовательность, удаляя значения, возвращенные базовым механизмом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>Параметры

*ядра*<br/>
Тип базового механизма.

*P*<br/>
**Размер блока**. Количество значений в каждом блоке.

*R*<br/>
**Используемый блок**. Количество используемых значений в каждом блоке. Остальные значения удаляются (`P` - `R`). **Предварительные условия**: `0 < R ≤ P`

## <a name="members"></a>Участники

||||
|-|-|-|
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|

Дополнительные сведения о членах механизма см. в разделе [\<random>](../standard-library/random.md).

## <a name="remarks"></a>Примечания

Этот класс шаблона описывает адаптер механизма, формирующий значения за счет удаления некоторых значений, возвращаемых базовым механизмом.

## <a name="requirements"></a>Требования

**Заголовок:** \<random>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<random>](../standard-library/random.md)<br/>
