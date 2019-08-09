---
title: Класс discard_block_engine
ms.date: 11/04/2016
f1_keywords:
- random/std::discard_block_engine
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
ms.openlocfilehash: 76a78a2f47bd160c6b2b981b1ccdda2ef3a90575
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454395"
---
# <a name="discardblockengine-class"></a>Класс discard_block_engine

Создает случайную последовательность, удаляя значения, возвращенные базовым механизмом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>Параметры

*Ядре*\
Тип базового механизма.

*Ш*\
**Размер блока**. Количество значений в каждом блоке.

*R*\
**Используемый блок**. Количество используемых значений в каждом блоке. Остальные отбрасываются (`P` - `R`). **Предварительные условия**: `0 < R ≤ P`

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

[\<random>](../standard-library/random.md)
