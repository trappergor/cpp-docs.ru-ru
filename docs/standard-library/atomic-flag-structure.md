---
title: Структура atomic_flag
ms.date: 11/04/2016
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
ms.openlocfilehash: 13af0c26b765aa7ebbbd1ec22b5a0ed1b8cce0ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550427"
---
# <a name="atomicflag-structure"></a>Структура atomic_flag

Описывает объект, который автоматически устанавливает и очищает **bool** флаг. Операции с атомарными флагами всегда неблокирующие.

## <a name="syntax"></a>Синтаксис

```cpp
struct atomic_flag;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[clear](#clear)|Устанавливает сохраненный флаг **false**.|
|[test_and_set](#test_and_set)|Устанавливает сохраненный флаг **true** и возвращает начальное значение флага.|

## <a name="remarks"></a>Примечания

Объекты `atomic_flag` могут передаваться в функции [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set) и [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit), которые не являются функциями-членами. Их можно инициализировать с помощью значения `ATOMIC_FLAG_INIT`.

## <a name="requirements"></a>Требования

**Заголовок:** \<atomic >

**Пространство имен:** std

## <a name="clear"></a>  atomic_flag::Clear

Наборы **bool** флаг, который хранится в `*this` для **false**, в течение указанного [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничения.

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Параметры

*Порядок*<br/>
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="test_and_set"></a>  atomic_flag::test_and_set

Наборы **bool** флаг, который хранится в `*this` для **true**, в течение указанного [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничения.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Параметры

*Порядок*<br/>
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Начальное значение флага, который хранится в `*this`.

## <a name="see-also"></a>См. также

[\<atomic>](../standard-library/atomic.md)<br/>
