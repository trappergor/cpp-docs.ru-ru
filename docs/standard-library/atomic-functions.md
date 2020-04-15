---
title: '&lt;Атомарные&gt; функции'
ms.date: 07/11/2018
f1_keywords:
- atomic/std::atomic_compare_exchange_strong
- atomic/std::atomic_compare_exchange_strong_explicit
- atomic/std::atomic_compare_exchange_weak
- atomic/std::atomic_compare_exchange_weak_explicit
- atomic/std::atomic_exchange
- atomic/std::atomic_exchange_explicit
- atomic/std::atomic_fetch_add
- atomic/std::atomic_fetch_add_explicit
- atomic/std::atomic_fetch_and
- atomic/std::atomic_fetch_and_explicit
- atomic/std::atomic_fetch_or
- atomic/std::atomic_fetch_or_explicit
- atomic/std::atomic_fetch_sub
- atomic/std::atomic_fetch_sub_explicit
- atomic/std::atomic_fetch_xor
- atomic/std::atomic_fetch_xor_explicit
- atomic/std::atomic_flag_clear
- atomic/std::atomic_flag_clear_explicit
- atomic/std::atomic_flag_test_and_set
- atomic/std::atomic_flag_test_and_set_explicit
- atomic/std::atomic_init
- atomic/std::atomic_is_lock_free
- atomic/std::atomic_load
- atomic/std::atomic_load_explicit
- atomic/std::atomic_signal_fence
- atomic/std::atomic_store
- atomic/std::atomic_store_explicit
- atomic/std::atomic_thread_fence
- atomic/std::kill_dependency
ms.assetid: 5c53b4f8-6ff5-47d7-beb2-2d6ee3c6ea89
helpviewer_keywords:
- std::atomic_compare_exchange_strong [C++]
- std::atomic_compare_exchange_strong_explicit [C++]
- std::atomic_compare_exchange_weak [C++]
- std::atomic_compare_exchange_weak_explicit [C++]
- std::atomic_exchange [C++]
- std::atomic_exchange_explicit [C++]
- std::atomic_fetch_add [C++]
- std::atomic_fetch_add_explicit [C++]
- std::atomic_fetch_and [C++]
- std::atomic_fetch_and_explicit [C++]
- std::atomic_fetch_or [C++]
- std::atomic_fetch_or_explicit [C++]
- std::atomic_fetch_sub [C++]
- std::atomic_fetch_sub_explicit [C++]
- std::atomic_fetch_xor [C++]
- std::atomic_fetch_xor_explicit [C++]
- std::atomic_flag_clear [C++]
- std::atomic_flag_clear_explicit [C++]
- std::atomic_flag_test_and_set [C++]
- std::atomic_flag_test_and_set_explicit [C++]
- std::atomic_init [C++]
- std::atomic_is_lock_free [C++]
- std::atomic_load [C++]
- std::atomic_load_explicit [C++]
- std::atomic_signal_fence [C++]
- std::atomic_store [C++]
- std::atomic_store_explicit [C++]
- std::atomic_thread_fence [C++]
- std::kill_dependency [C++]
ms.openlocfilehash: b6d03da446e4a3bae02f662e5b106bd5de534d0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376888"
---
# <a name="ltatomicgt-functions"></a>&lt;Атомарные&gt; функции

||||
|-|-|-|
|[atomic_compare_exchange_strong](#atomic_compare_exchange_strong)|[atomic_compare_exchange_strong_explicit](#atomic_compare_exchange_strong_explicit)|[atomic_compare_exchange_weak](#atomic_compare_exchange_weak)|
|[atomic_compare_exchange_weak_explicit](#atomic_compare_exchange_weak_explicit)|[atomic_exchange](#atomic_exchange)|[atomic_exchange_explicit](#atomic_exchange_explicit)|
|[atomic_fetch_add](#atomic_fetch_add)|[atomic_fetch_add_explicit](#atomic_fetch_add_explicit)|[atomic_fetch_and](#atomic_fetch_and)|
|[atomic_fetch_and_explicit](#atomic_fetch_and_explicit)|[atomic_fetch_or](#atomic_fetch_or)|[atomic_fetch_or_explicit](#atomic_fetch_or_explicit)|
|[atomic_fetch_sub](#atomic_fetch_sub)|[atomic_fetch_sub_explicit](#atomic_fetch_sub_explicit)|[atomic_fetch_xor](#atomic_fetch_xor)|
|[atomic_fetch_xor_explicit](#atomic_fetch_xor_explicit)|[atomic_flag_clear](#atomic_flag_clear)|[atomic_flag_clear_explicit](#atomic_flag_clear_explicit)|
|[atomic_flag_test_and_set](#atomic_flag_test_and_set)|[atomic_flag_test_and_set_explicit](#atomic_flag_test_and_set_explicit)|[atomic_init](#atomic_init)|
|[atomic_is_lock_free](#atomic_is_lock_free)|[atomic_load](#atomic_load)|[atomic_load_explicit](#atomic_load_explicit)|
|[atomic_signal_fence](#atomic_signal_fence)|[atomic_store](#atomic_store)|[atomic_store_explicit](#atomic_store_explicit)|
|[atomic_thread_fence](#atomic_thread_fence)|[kill_dependency](#kill_dependency)|

## <a name="atomic_compare_exchange_strong"></a><a name="atomic_compare_exchange_strong"></a>atomic_compare_exchange_strong

Выполняет атомарную операцию сравнения и обмена.

```cpp
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на *атомный* объект, который `Ty`хранит значение типа.

*Exp*\
Указатель на значение типа `Ty`.

*Значение*\
Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если значения равны, в противном случае **ложные**.

### <a name="remarks"></a>Remarks

Этот метод выполняет атомарную операцию сравнения и обмена с помощью неявных аргументов `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum). Дополнительные сведения см. в разделе [atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit).

## <a name="atomic_compare_exchange_strong_explicit"></a><a name="atomic_compare_exchange_strong_explicit"></a>atomic_compare_exchange_strong_explicit

Выполняет *атомарную операцию сравнения и обмена*.

```cpp
template <class T>
inline bool atomic_compare_exchange_strong_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Exp*\
Указатель на значение типа `Ty`.

*Значение*\
Значение типа `Ty`.

*Заказ1*\
Первый аргумент [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

*Заказ2*\
Второй аргумент `memory_order`. Значение *Order2* не `memory_order_release` может `memory_order_acq_rel`быть или, оно не может быть сильнее, чем значение *Order1.*

### <a name="return-value"></a>Возвращаемое значение

**верно,** если значения равны, в противном случае **ложные**.

### <a name="remarks"></a>Remarks

*Операция атомного сравнения и обмена* сравнивает значение, которое хранится в объекте, на которое указывает *Atom,* с значением, на которое указывает *Exp.* Если значения равны, значение, хранящееся в объекте, на которое указывает `read-modify-write` *атом,* заменяется *значением* с помощью операции и применяя ограничения порядка памяти, указанные *Order1.* Если значения не равны, операция заменяет значение, на которое указывает *Exp,* на значение, которое хранится в объекте, на которое указывает *Atom,* и применяет ограничения порядка памяти, указанные *Order2.*

## <a name="atomic_compare_exchange_weak"></a><a name="atomic_compare_exchange_weak"></a>atomic_compare_exchange_weak

Выполняет *слабую атомарную операцию сравнения и обмена*.

```cpp
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Exp*\
Указатель на значение типа `Ty`.

*Значение*\
Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если значения равны, в противном случае **ложные**.

### <a name="remarks"></a>Remarks

Этот метод выполняет *слабую атомарную операцию сравнения и обмена* с помощью неявных аргументов `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum). Дополнительные сведения см. в разделе [atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit).

## <a name="atomic_compare_exchange_weak_explicit"></a><a name="atomic_compare_exchange_weak_explicit"></a>atomic_compare_exchange_weak_explicit

Выполняет *слабую атомарную операцию сравнения и обмена*.

```cpp
template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Exp*\
Указатель на значение типа `Ty`.

*Значение*\
Значение типа `Ty`.

*Заказ1*\
Первый аргумент [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

*Заказ2*\
Второй аргумент `memory_order`. Значение *Order2* не `memory_order_release` может `memory_order_acq_rel`быть или, и не может быть сильнее, чем значение *Order1.*

### <a name="return-value"></a>Возвращаемое значение

**верно,** если значения равны, в противном случае **ложные**.

### <a name="remarks"></a>Remarks

Как сильные, так и слабые вкусы *атомной операции сравнения и обмена* гарантируют, что они не хранят новое значение, если ожидаемые и текущие значения не равны. Сильный вкус гарантирует, что он будет хранить новое значение, если ожидаемые и текущие значения равны. Слабый вкус может иногда возвращать **ложное** и не хранить новое значение, даже если текущие и ожидаемые значения равны. Другими словами, функция вернется **ложной,** но более позднее изучение ожидаемого значения может показать, что оно не изменилось, и поэтому должно было сравниться как равное.

## <a name="atomic_exchange"></a><a name="atomic_exchange"></a>atomic_exchange

Использует *значение* для замены хранимой стоимости *Atom.*

```cpp
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Значение*\
Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Сохраненная стоимость *Atom* перед обменом.

### <a name="remarks"></a>Remarks

Функция `atomic_exchange` выполняет операцию по `read-modify-write` обмену значения, которое хранится в *Atom,* с помощью *Value* `memory_order_seq_cst` [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

## <a name="atomic_exchange_explicit"></a><a name="atomic_exchange_explicit"></a>atomic_exchange_explicit

Заменяет хранимые значения *Atom* на *значение.*

```cpp
template <class Ty>
inline Ty atomic_exchange_explicit(
    volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_exchange_explicit(
    atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Значение*\
Значение типа `Ty`.

*Заказ*\
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Сохраненная стоимость *Atom* перед обменом.

### <a name="remarks"></a>Remarks

Функция `atomic_exchange_explicit` выполняет операцию по `read-modify-write` обмену значения, которое хранится в *Atom,* с *значением,* в пределах ограничений памяти, указанных *Заказом.*

## <a name="atomic_fetch_add"></a><a name="atomic_fetch_add"></a>atomic_fetch_add

Добавляет значение к существующему значению, хранящемуся в объекте `atomic`.

```cpp
template <class T>
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит указатель на тип `T`.

*Значение*\
Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Remarks

Функция `atomic_fetch_add` выполняет операцию `read-modify-write` по атомарному добавлению *значения* к сохраненной стоимости в *Atom,* используя `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничение.

Когда атомный `atomic_address`тип, *Значение* имеет тип `ptrdiff_t` и операция рассматривает `char *`сохраненный указатель как .

Эта операция также перегружается для целочисленных типов:

```cpp
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_add_explicit"></a><a name="atomic_fetch_add_explicit"></a>atomic_fetch_add_explicit

Добавляет значение к существующему значению, хранящемуся в объекте `atomic`.

```cpp
template <class T>
T* atomic_fetch_add_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>
T* atomic_fetch_add_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит указатель на тип `T`.

*Значение*\
Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Remarks

Функция `atomic_fetch_add_explicit` выполняет операцию `read-modify-write` по атомарному добавлению *значения* к сохраненному значению в *Atom,* в пределах [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничений, указанных `Order`.

Когда атомарным типом является `atomic_address`, `Value` имеет тип `ptrdiff_t`, и операция считает, что тип сохраненного указателя — `char *`.

Эта операция также перегружается для целочисленных типов:

```cpp
integral atomic_fetch_add_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_add_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```

## <a name="atomic_fetch_and"></a><a name="atomic_fetch_and"></a>atomic_fetch_and

Выполняет побитовую операцию `and` со значением и существующим значением, хранящимся в объекте `atomic`.

```cpp
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*\
Значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Remarks

Функция `atomic_fetch_and` `read-modify-write` выполняет операцию по замене сохраненного значения *Atom* на битное `and` *значение* и текущее значение, которое хранится в *Atom,* используя `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничение.

## <a name="atomic_fetch_and_explicit"></a><a name="atomic_fetch_and_explicit"></a>atomic_fetch_and_explicit

Выполняет побитовую операцию `and` со значением и существующим значением, хранящимся в объекте `atomic`.

```cpp
template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*\
Значение типа `T`.

*Заказ*\
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Remarks

Функция `atomic_fetch_and_explicit` выполняет операцию `read-modify-write` по замене сохраненного значения *Atom* на битное `and` *значение* и текущее значение, которое хранится в *Atom,* в пределах ограничений памяти, указанных *Порядком.*

## <a name="atomic_fetch_or"></a><a name="atomic_fetch_or"></a>atomic_fetch_or

Выполняет побитовую операцию `or` со значением и существующим значением, хранящимся в объекте `atomic`.

```cpp
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*\
Значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Remarks

Функция `atomic_fetch_or` `read-modify-write` выполняет операцию по замене хранимой стоимости *Atom* на битную `or` *стоимость* и текущее значение, которое хранится в *Atom,* используя `memory_order_seq_cst` [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

## <a name="atomic_fetch_or_explicit"></a><a name="atomic_fetch_or_explicit"></a>atomic_fetch_or_explicit

Выполняет побитовую операцию `or` со значением и существующим значением, хранящимся в объекте `atomic`.

```cpp
template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*\
Значение типа `T`.

*Заказ*\
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Remarks

Функция `atomic_fetch_or_explicit` выполняет `read-modify-write` операцию по замене сохраненного значения *Atom* на битное `or` *значение* и текущее значение, которое хранится в *Atom,* в пределах [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничений, указанных *Порядком.*

## <a name="atomic_fetch_sub"></a><a name="atomic_fetch_sub"></a>atomic_fetch_sub

Вычитает значение из существующего значения, хранящегося в объекте `atomic`.

```cpp
template <class T>
T* atomic_fetch_sub(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;

template <class T>
T* atomic_fetch_sub(
    atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит указатель на тип `T`.

*Значение*\
Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Remarks

Функция `atomic_fetch_sub` выполняет операцию `read-modify-write` по атомарной вычитанию *значения* из хранимого значения в *Atom,* используя `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничение.

Когда атомный `atomic_address`тип, *Значение* имеет тип `ptrdiff_t` и операция рассматривает `char *`сохраненный указатель как .

Эта операция также перегружается для целочисленных типов:

```cpp
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_sub_explicit"></a><a name="atomic_fetch_sub_explicit"></a>atomic_fetch_sub_explicit

Вычитает значение из существующего значения, хранящегося в объекте `atomic`.

```cpp
template <class T>
T* atomic_fetch_sub_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>
T* atomic_fetch_sub_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value, memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит указатель на тип `T`.

*Значение*\
Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Remarks

Функция `atomic_fetch_sub_explicit` выполняет операцию `read-modify-write` по атомарному вычитанию *значения* из хранимого значения в *Atom,* в пределах [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничений, указанных `Order`.

Когда атомный `atomic_address`тип, *Значение* имеет тип `ptrdiff_t` и операция рассматривает `char *`сохраненный указатель как .

Эта операция также перегружается для целочисленных типов:

```cpp
integral atomic_fetch_sub_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_sub_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```

## <a name="atomic_fetch_xor"></a><a name="atomic_fetch_xor"></a>atomic_fetch_xor

Выполняет побитовую операцию `exclusive or` со значением и существующим значением, хранящимся в объекте `atomic`.

```cpp
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*\
Значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Remarks

Функция `atomic_fetch_xor` `read-modify-write` выполняет операцию по замене хранимой стоимости *Atom* на битную `exclusive or` *стоимость* и текущее значение, которое хранится в *Atom,* используя `memory_order_seq_cst` [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

## <a name="atomic_fetch_xor_explicit"></a><a name="atomic_fetch_xor_explicit"></a>atomic_fetch_xor_explicit

Выполняет побитовую операцию `exclusive or` со значением и существующим значением, хранящимся в объекте `atomic`.

```cpp
template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*\
Значение типа `T`.

*Заказ*\
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Remarks

Функция `atomic_fetch_xor_explicit` выполняет `read-modify-write` операцию по замене сохраненного значения *Atom* на битное `exclusive or` *значение* и текущее значение, которое хранится в *Atom,* в пределах [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничений, указанных *Порядком.*

## <a name="atomic_flag_clear"></a><a name="atomic_flag_clear"></a>atomic_flag_clear

Устанавливает **флаг bool** в [atomic_flag](../standard-library/atomic-flag-structure.md) объект к `memory_order_seq_cst` **ложным,** в пределах [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

```cpp
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```

### <a name="parameters"></a>Параметры

*Флаг*\
Указатель на объект `atomic_flag`.

## <a name="atomic_flag_clear_explicit"></a><a name="atomic_flag_clear_explicit"></a>atomic_flag_clear_explicit

Устанавливает флаг **bool** в [atomic_flag](../standard-library/atomic-flag-structure.md) **объекте ложному,** в пределах указанных [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничений.

```cpp
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Флаг*\
Указатель на объект `atomic_flag`.

*Заказ*\
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_flag_test_and_set"></a><a name="atomic_flag_test_and_set"></a>atomic_flag_test_and_set

Устанавливает **флаг bool** в [atomic_flag](../standard-library/atomic-flag-structure.md) возражают против **истинности,** в пределах ограничений `memory_order_seq_cst` [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

```cpp
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```

### <a name="parameters"></a>Параметры

*Флаг*\
Указатель на объект `atomic_flag`.

### <a name="return-value"></a>Возвращаемое значение

Начальное значение *флага*.

## <a name="atomic_flag_test_and_set_explicit"></a><a name="atomic_flag_test_and_set_explicit"></a>atomic_flag_test_and_set_explicit

Устанавливает флаг **bool** в [atomic_flag](../standard-library/atomic-flag-structure.md) объект к **истине,** в пределах указанных [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничений.

```cpp
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Флаг*\
Указатель на объект `atomic_flag`.

*Заказ*\
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Начальное значение *флага*.

## <a name="atomic_init"></a><a name="atomic_init"></a>atomic_init

Задает сохраненное значение в объекте `atomic`.

```cpp
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Значение*\
Значение типа `Ty`.

### <a name="remarks"></a>Remarks

`atomic_init` не является атомарной операцией. Этот указатель не является потокобезопасным.

## <a name="atomic_is_lock_free"></a><a name="atomic_is_lock_free"></a>atomic_is_lock_free

Указывает, являются ли операции с объектом `atomic`*неблокирующими*.

```cpp
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который хранит значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если атомные операции на *Атоме* не имеют блокировки; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Атомарный тип является неблокирующим, если никакие атомарные операции с этим типом не используют блокировки. Если эта функция возвращает значение true, тип можно безопасно использовать в обработчиках сигналов.

## <a name="atomic_load"></a><a name="atomic_load"></a>atomic_load

Извлекает сохраненное значение в объект `atomic`.

```cpp
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который содержит значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Извлеченное значение, хранящееся в *Atom*.

### <a name="remarks"></a>Remarks

`atomic_load`неявно использует `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_load_explicit"></a><a name="atomic_load_explicit"></a>atomic_load_explicit

Извлекает сохраненное значение в объект `atomic` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который содержит значение типа `Ty`.

*Заказ*\
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Не используйте `memory_order_release``memory_order_acq_rel`.

### <a name="return-value"></a>Возвращаемое значение

Извлеченное значение, хранящееся в *Atom*.

## <a name="atomic_signal_fence"></a><a name="atomic_signal_fence"></a>atomic_signal_fence

Действует как *граница* — это примитив синхронизации памяти, который обеспечивает порядок между операциями загрузки или сохранения — между другими границами в вызывающем потоке, которые имеют обработчики сигнала, выполняющиеся в одном потоке.

```cpp
inline void atomic_signal_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Заказ*\
Ограничение порядка памяти, которое определяет тип границы.

### <a name="remarks"></a>Remarks

Аргумент *Заказа* определяет тип забора.

|||
|-|-|
|`memory_order_relaxed`|Граница не действует.|
|`memory_order_consume`|Граница является границей получения.|
|`memory_order_acquire`|Граница является границей получения.|
|`memory_order_release`|Граница является границей выпуска.|
|`memory_order_acq_rel`|Граница является и границей получения, и границей выпуска.|
|`memory_order_seq_cst`|Граница является и границей получения, и границей выпуска, и она также последовательно согласованная.|

## <a name="atomic_store"></a><a name="atomic_store"></a>atomic_store

Атомарным образом сохраняет значение в атомарном объекте.

```cpp
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на атомарный объект, который содержит значение типа `Ty`.

*Значение*\
Значение типа `Ty`.

### <a name="remarks"></a>Remarks

`atomic_store`хранит *Значение* в объекте, на который указывает `memory_order_seq_cst` *Atom,* в пределах [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничения.

## <a name="atomic_store_explicit"></a><a name="atomic_store_explicit"></a>atomic_store_explicit

Атомарным образом сохраняет значение в атомарном объекте.

```cpp
template <class Ty>
inline Ty atomic_store_explicit(
    const volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_store_explicit(
    const atomic<Ty>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Атом*\
Указатель на объект `atomic`, который содержит значение типа `Ty`.

*Значение*\
Значение типа `Ty`.

*Заказ*\
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Не используйте `memory_order_consume`, `memory_order_acquire` или `memory_order_acq_rel`.

### <a name="remarks"></a>Remarks

`atomic_store`хранилища *Значение* в объекте, который указывается `memory_order` на *Atom*, в пределах, что указано в *Порядке*.

## <a name="atomic_thread_fence"></a><a name="atomic_thread_fence"></a>atomic_thread_fence

Действует как *граница* — это примитив синхронизации памяти, который обеспечивает порядок между операциями загрузки или сохранения — без связанной атомарной операции.

```cpp
inline void atomic_thread_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Заказ*\
Ограничение порядка памяти, которое определяет тип границы.

### <a name="remarks"></a>Remarks

Аргумент *Заказа* определяет тип забора.

|||
|-|-|
|`memory_order_relaxed`|Граница не действует.|
|`memory_order_consume`|Граница является границей получения.|
|`memory_order_acquire`|Граница является границей получения.|
|`memory_order_release`|Граница является границей выпуска.|
|`memory_order_acq_rel`|Граница является и границей получения, и границей выпуска.|
|`memory_order_seq_cst`|Граница является и границей получения, и границей выпуска, и она также последовательно согласованная.|

## <a name="kill_dependency"></a><a name="kill_dependency"></a>kill_dependency

Удаляет зависимость.

```cpp
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```

### <a name="parameters"></a>Параметры

*Arg*\
Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Значение возврата *Arg*. Оценка *Arg* не несет в себе зависимость от вызова функции. Разбивая возможную цепочку зависимостей, функция позволяет компилятору создавать более эффективный код.

## <a name="see-also"></a>См. также раздел

[\<атомный>](../standard-library/atomic.md)
