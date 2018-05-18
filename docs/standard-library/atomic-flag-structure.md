---
title: Структура atomic_flag | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
dev_langs:
- C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06959bd5a22c65077f447f0f0e776025cbe5ced5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="atomicflag-structure"></a>Структура atomic_flag

Описывает объект, который автоматически устанавливает и очищает флаг `bool`. Операции с атомарными флагами всегда неблокирующие.

## <a name="syntax"></a>Синтаксис

```cpp
struct atomic_flag;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[clear](#clear)|Устанавливает сохраненный флаг в значение `false`.|
|[test_and_set](#test_and_set)|Устанавливает сохраненный флаг в значение `true` и возвращает начальное значение флага.|

## <a name="remarks"></a>Примечания

Объекты `atomic_flag` могут передаваться в функции [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set) и [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit), которые не являются функциями-членами. Их можно инициализировать с помощью значения `ATOMIC_FLAG_INIT`.

## <a name="requirements"></a>Требования

**Заголовок:** \<atomic >

**Пространство имен:** std

## <a name="clear"></a>  atomic_flag::Clear

Устанавливает флаг `bool`, хранящийся в объекте `*this``false` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Параметры

`Order` Объект [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="test_and_set"></a>  atomic_flag::test_and_set

Устанавливает флаг `bool`, хранящийся в объекте `*this``true` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Параметры

`Order` Объект [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Начальное значение флага, который хранится в `*this`.

## <a name="see-also"></a>См. также

[\<atomic>](../standard-library/atomic.md)<br/>
