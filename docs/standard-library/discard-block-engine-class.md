---
title: Класс discard_block_engine | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- random/std::discard_block_engine
dev_langs:
- C++
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59136111b6d4f594d84040c02270b219ad55ae0f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="discardblockengine-class"></a>Класс discard_block_engine

Создает случайную последовательность, удаляя значения, возвращенные базовым механизмом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>Параметры

`Engine` Тип базового механизма.

`P` **Размер блока**. Количество значений в каждом блоке.

`R` **Используемый блок**. Количество используемых значений в каждом блоке. Остальные значения удаляются (`P` - `R`). **Предварительные условия**: `0 < R ≤ P`

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
