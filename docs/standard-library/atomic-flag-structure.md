---
title: Структура atomic_flag
ms.date: 11/04/2016
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
ms.openlocfilehash: ad4b6dcaf6db1a8abe5b81b4d630e84b54fbaa63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376872"
---
# <a name="atomic_flag-structure"></a>Структура atomic_flag

Описывает объект, который атомарно устанавливает и очищает флаг **bool.** Операции с атомарными флагами всегда неблокирующие.

## <a name="syntax"></a>Синтаксис

```cpp
struct atomic_flag;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Ясно](#clear)|Устанавливает сохраненный флаг на **ложный**.|
|[test_and_set](#test_and_set)|Устанавливает сохраненный флаг на **истину** и возвращает начальное значение флага.|

## <a name="remarks"></a>Remarks

Объекты `atomic_flag` могут передаваться в функции [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set) и [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit), которые не являются функциями-членами. Их можно инициализировать с помощью значения `ATOMIC_FLAG_INIT`.

## <a name="requirements"></a>Требования

**Заголовок:** \<атомный>

**Пространство имен:** std

## <a name="atomic_flagclear"></a><a name="clear"></a>atomic_flag::ясно

Устанавливает флаг **bool,** который `*this` хранится в **ложном,** в пределах указанного [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничений.

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Параметры

*Заказ*\
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_flagtest_and_set"></a><a name="test_and_set"></a>atomic_flag::test_and_set

Устанавливает флаг **bool,** который `*this` хранится в **истинном,** в пределах указанного [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничений.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Параметры

*Заказ*\
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Начальное значение флага, который хранится в `*this`.

## <a name="see-also"></a>См. также раздел

[\<атомный>](../standard-library/atomic.md)
