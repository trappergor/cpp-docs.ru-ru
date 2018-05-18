---
title: '&lt;Атомарные&gt; функции | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: mikeblome
ms.author: mblome
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
ms.workload:
- cplusplus
ms.openlocfilehash: 50e70230dd5b8d9aa61f4df8c1288569192048b0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
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

## <a name="atomic_compare_exchange_strong"></a>  atomic_compare_exchange_strong

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

`Atom` Указатель на `atomic` объекта, который хранит значение типа `Ty`.

`Exp` Указатель на значение типа `Ty`.

`Value` Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Логическое значение `bool`, указывающее результат сравнения значений.

### <a name="remarks"></a>Примечания

Этот метод выполняет атомарную операцию сравнения и обмена с помощью неявных аргументов `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Дополнительные сведения см. в разделе [atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit).

## <a name="atomic_compare_exchange_strong_explicit"></a>  atomic_compare_exchange_strong_explicit

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

`Atom` Указатель на `atomic` объекта, который хранит значение типа `Ty`.

`Exp` Указатель на значение типа `Ty`.

`Value` Значение типа `Ty`.

`Order1` Первый [memory_order](../standard-library/atomic-enums.md#memory_order_enum) аргумент.

`Order2` Второй `memory_order` аргумент. Значение `Order2` не может быть `memory_order_release` или `memory_order_acq_rel`, и оно не может быть надежнее, чем значение `Order1`.

### <a name="return-value"></a>Возвращаемое значение

Логическое значение `bool`, указывающее результат сравнения значений.

### <a name="remarks"></a>Примечания

*Атомарная операция сравнения и обмена* сравнивает значение, хранящееся в объекте, на который указывает `Atom`, со значением, на которое указывает `Exp`. Если значения равны, то значение, хранящееся в объекте, на который указывает `atom`, заменяется на `Val` с помощью операции `read-modify-write` и применения ограничений порядка памяти, которые задаются с помощью `Order1`. Если значения не равны, операция заменяет значение, указанное `Exp`, на значение, хранящееся в объекте, на который указывает `Atom`, и применяет ограничения порядка памяти, которые задаются с помощью `Order2`.

## <a name="atomic_compare_exchange_weak"></a>  atomic_compare_exchange_weak

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

`Atom` Указатель на `atomic` объекта, который хранит значение типа `Ty`.

`Exp` Указатель на значение типа `Ty`.

`Value` Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Логическое значение `bool`, указывающее результат сравнения значений.

### <a name="remarks"></a>Примечания

Этот метод выполняет *слабую атомарную операцию сравнения и обмена* с помощью неявных аргументов `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum). Дополнительные сведения см. в разделе [atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit).

## <a name="atomic_compare_exchange_weak_explicit"></a>  atomic_compare_exchange_weak_explicit

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

`Atom` Указатель на `atomic` объекта, который хранит значение типа `Ty`.

`Exp` Указатель на значение типа `Ty`.

`Value` Значение типа `Ty`.

`Order1` Первый [memory_order](../standard-library/atomic-enums.md#memory_order_enum) аргумент.

`Order2` Второй `memory_order` аргумент. Значение `Order2` не может быть `memory_order_release` или `memory_order_acq_rel`, и оно не может быть надежнее, чем значение `Order1`.

### <a name="return-value"></a>Возвращаемое значение

Логическое значение `bool`, указывающее результат сравнения значений.

### <a name="remarks"></a>Примечания

*Атомарная операция сравнения и обмена* сравнивает значение, хранящееся в объекте, на который указывает `Atom`, со значением, указанным `Exp`. Если значения равны, то операция заменяет значение, хранящееся в объекте, на который указывает `Atom`, на `Val` с помощью операции `read-modify-write` и применения ограничений порядка памяти, которые задаются с помощью `Order1`. Если значения не равны, операция заменяет значение, указанное `Exp`, на значение, хранящееся в объекте, на который указывает `Atom`, и применяет ограничения порядка памяти, которые задаются с помощью `Order2`.

*Слабая* атомарная операция сравнения и обмена выполняет обмен, если сравниваемые значения равны. Однако если значения не равны, операция необязательно выполнит обмен.

## <a name="atomic_exchange"></a>  atomic_exchange

Использует `Value` для замены сохраненного значения `Atom`.

```cpp
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Параметры

`Atom` Указатель на `atomic` объекта, который хранит значение типа `Ty`.

`Value` Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Сохраненное значение `Atom` до обмена.

### <a name="remarks"></a>Примечания

Функция `atomic_exchange` выполняет операцию `read-modify-write` для обмена значения, которое хранится в `Atom`, на `Value`, используя `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_exchange_explicit"></a>  atomic_exchange_explicit

Заменяет значение, хранящееся в `Atom`, на `Value`.

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

`Atom` Указатель на `atomic` объекта, который хранит значение типа `Ty`.

`Value` Значение типа `Ty`.

`Order` Объект [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Сохраненное значение `Atom` до обмена.

### <a name="remarks"></a>Примечания

Функция `atomic_exchange_explicit` выполняет операцию `read-modify-write` для обмена значения, которое хранится в `Atom`, на `Value` с соблюдением ограничений памяти, которые задаются с помощью `Order`.

## <a name="atomic_fetch_add"></a>  atomic_fetch_add

Добавляет значение к существующему значению, хранящемуся в объекте `atomic`.

```cpp
template <class T>
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Параметры

`Atom` Указатель на `atomic` объекта, который хранит указатель на тип `T`.

`Value` Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

Функция `atomic_fetch_add` выполняет операцию `read-modify-write`, чтобы атомарным образом добавить `Value` к значению, хранящемуся в `Atom`, используя ограничение `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

Когда атомарным типом является `atomic_address`, `Value` имеет тип `ptrdiff_t`, и операция считает, что тип сохраненного указателя — `char *`.

Эта операция также перегружается для целочисленных типов:

```cpp
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_add_explicit"></a>  atomic_fetch_add_explicit

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

`Atom` Указатель на `atomic` объекта, который хранит указатель на тип `T`.

`Value` Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

Функция `atomic_fetch_add_explicit` выполняет операцию `read-modify-write`, чтобы атомарным образом добавить `Value` к сохраненному значению в `Atom` с соблюдением ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum)`Order`.

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

## <a name="atomic_fetch_and"></a>  atomic_fetch_and

Выполняет побитовую операцию `and` со значением и существующим значением, хранящимся в объекте `atomic`.

```cpp
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Параметры

`Atom` Указатель на `atomic` объекта, который хранит значение типа `T`.

`Value` Значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

Функция `atomic_fetch_and` выполняет операцию `read-modify-write`, чтобы заменить значение, хранящееся в `Atom`, на результат побитовой операции `and` с `Value` и текущим значением, хранящимся в `Atom`, с использованием ограничения `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_fetch_and_explicit"></a>  atomic_fetch_and_explicit

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

`Atom` Указатель на `atomic` объекта, который хранит значение типа `T`.

`Value` Значение типа `T`.

`Order` Объект [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

Функция `atomic_fetch_and_explicit` выполняет операцию `read-modify-write`, чтобы заменить сохраненное значение `Atom` на результат побитовой операции `and` с `Value` и текущим значением, хранящимся в `Atom`, с соблюдением ограничений, заданных с помощью `Order`.

## <a name="atomic_fetch_or"></a>  atomic_fetch_or

Выполняет побитовую операцию `or` со значением и существующим значением, хранящимся в объекте `atomic`.

```cpp
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Параметры

`Atom` Указатель на `atomic` объекта, который хранит значение типа `T`.

`Value` Значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

Функция `atomic_fetch_or` выполняет операцию `read-modify-write`, чтобы заменить сохраненное значение `Atom` на результат побитовой операции `or` с `Value` и текущим значением, хранящимся в `Atom`, с использованием `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_fetch_or_explicit"></a>  atomic_fetch_or_explicit

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

`Atom` Указатель на `atomic` объекта, который хранит значение типа `T`.

`Value` Значение типа `T`.

`Order` Объект [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

Функция `atomic_fetch_or_explicit` выполняет операцию `read-modify-write`, чтобы заменить сохраненное значение `Atom` на результат побитовой операции `or` с `Value` и текущим значением, хранящимся в `Atom`, с соблюдением ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum), заданных с помощью `Order`.

## <a name="atomic_fetch_sub"></a>  atomic_fetch_sub

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

`Atom` Указатель на `atomic` объекта, который хранит указатель на тип `T`.

`Value` Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

Функция `atomic_fetch_sub` выполняет операцию `read-modify-write`, чтобы атомарным образом вычесть `Value` из значения, хранящегося в `Atom`, используя ограничение `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

Когда атомарным типом является `atomic_address`, `Value` имеет тип `ptrdiff_t`, и операция считает, что тип сохраненного указателя — `char *`.

Эта операция также перегружается для целочисленных типов:

```cpp
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_sub_explicit"></a>  atomic_fetch_sub_explicit

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

`Atom` Указатель на `atomic` объекта, который хранит указатель на тип `T`.

`Value` Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

Функция `atomic_fetch_sub_explicit` выполняет операцию `read-modify-write`, чтобы атомарным образом вычесть `Value` из значения, хранящегося в `Atom`, с соблюдением ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum), заданных с помощью `Order`.

Когда атомарным типом является `atomic_address`, `Value` имеет тип `ptrdiff_t`, и операция считает, что тип сохраненного указателя — `char *`.

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

## <a name="atomic_fetch_xor"></a>  atomic_fetch_xor

Выполняет побитовую операцию `exclusive or` со значением и существующим значением, хранящимся в объекте `atomic`.

```cpp
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Параметры

`Atom` Указатель на `atomic` объекта, который хранит значение типа `T`.

`Value` Значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

Функция `atomic_fetch_xor` выполняет операцию `read-modify-write`, чтобы заменить сохраненное значение `Atom` на результат побитовой операции `exclusive or` с `Value` и текущим значением, хранящимся в `Atom`, с использованием `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_fetch_xor_explicit"></a>  atomic_fetch_xor_explicit

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

`Atom` Указатель на `atomic` объекта, который хранит значение типа `T`.

`Value` Значение типа `T`.

`Order` Объект [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

Функция `atomic_fetch_xor_explicit` выполняет операцию `read-modify-write`, чтобы заменить сохраненное значение `Atom` на результат побитовой операции `exclusive or` с `Value` и текущим значением, хранящимся в `Atom`, с соблюдением ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum), заданных с помощью `Order`.

## <a name="atomic_flag_clear"></a>  atomic_flag_clear

Устанавливает флаг `bool` в объекте [atomic_flag](../standard-library/atomic-flag-structure.md) в значение `false` с соблюдением ограничений `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```

### <a name="parameters"></a>Параметры

`Flag` Указатель на `atomic_flag` объект.

## <a name="atomic_flag_clear_explicit"></a>  atomic_flag_clear_explicit

Устанавливает флаг `bool` в объекте [atomic_flag](../standard-library/atomic-flag-structure.md) в значение `false` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

`Flag` Указатель на `atomic_flag` объект.

`Order` Объект [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_flag_test_and_set"></a>  atomic_flag_test_and_set

Устанавливает флаг `bool` в объекте [atomic_flag](../standard-library/atomic-flag-structure.md) в значение `true` с соблюдением ограничений `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```

### <a name="parameters"></a>Параметры

`Flag` Указатель на `atomic_flag` объект.

### <a name="return-value"></a>Возвращаемое значение

Начальное значение `Flag`.

## <a name="atomic_flag_test_and_set_explicit"></a>  atomic_flag_test_and_set_explicit

Устанавливает флаг `bool` в объекте [atomic_flag](../standard-library/atomic-flag-structure.md) в значение `true` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

`Flag` Указатель на `atomic_flag` объект.

`Order` Объект [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Начальное значение `Flag`.

## <a name="atomic_init"></a>  atomic_init

Задает сохраненное значение в объекте `atomic`.

```cpp
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Параметры

`Atom` Указатель на `atomic` объекта, который хранит значение типа `Ty`.

`Value` Значение типа `Ty`.

### <a name="remarks"></a>Примечания

`atomic_init` не является атомарной операцией. Этот указатель не является потокобезопасным.

## <a name="atomic_is_lock_free"></a>  atomic_is_lock_free

Указывает, являются ли операции с объектом `atomic` *неблокирующими*.

```cpp
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```

### <a name="parameters"></a>Параметры

`Atom` Указатель на `atomic` объекта, который хранит значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

Значение `true`, если атомарные операции с `Atom` являются неблокирующими; в противном случае — значение `false`.

### <a name="remarks"></a>Примечания

Атомарный тип является неблокирующим, если никакие атомарные операции с этим типом не используют блокировки. Если эта функция возвращает значение true, тип можно безопасно использовать в обработчиках сигналов.

## <a name="atomic_load"></a>  atomic_load

Извлекает сохраненное значение в объект `atomic`.

```cpp
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```

### <a name="parameters"></a>Параметры

`Atom` Указатель на `atomic` объект, содержащий значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Извлеченное значение, которое хранится в `Atom`.

### <a name="remarks"></a>Примечания

`atomic_load`неявно использует `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_load_explicit"></a>  atomic_load_explicit

Извлекает сохраненное значение в объект `atomic` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

`Atom` Указатель на `atomic` объект, содержащий значение типа `Ty`.

`Order` Объект [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Не используйте `memory_order_release``memory_order_acq_rel`.

### <a name="return-value"></a>Возвращаемое значение

Извлеченное значение, которое хранится в `Atom`.

## <a name="atomic_signal_fence"></a>  atomic_signal_fence

Действует как *граница* — это примитив синхронизации памяти, который обеспечивает порядок между операциями загрузки или сохранения — между другими границами в вызывающем потоке, которые имеют обработчики сигнала, выполняющиеся в одном потоке.

```cpp
inline void atomic_signal_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

`Order` Объем памяти, упорядочение ограничение, которое определяет тип границы.

### <a name="remarks"></a>Примечания

Аргумент `Order` определяет тип границы.

|||
|-|-|
|`memory_order_relaxed`|Граница не действует.|
|`memory_order_consume`|Граница является границей получения.|
|`memory_order_acquire`|Граница является границей получения.|
|`memory_order_release`|Граница является границей выпуска.|
|`memory_order_acq_rel`|Граница является и границей получения, и границей выпуска.|
|`memory_order_seq_cst`|Граница является и границей получения, и границей выпуска, и она также последовательно согласованная.|

## <a name="atomic_store"></a>  atomic_store

Атомарным образом сохраняет значение в атомарном объекте.

```cpp
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Параметры

`Atom` Указатель на объект atomic, который содержит значение типа `Ty`.

`Value` Значение типа `Ty`.

### <a name="remarks"></a>Примечания

`atomic_store` хранит `Value` в объекте, указанном `Atom`, с соблюдением ограничения `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_store_explicit"></a>  atomic_store_explicit

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

`Atom` Указатель на `atomic` объект, содержащий значение типа `Ty`.

`Value` Значение типа `Ty`.

`Order` Объект [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Не используйте `memory_order_consume`, `memory_order_acquire` или `memory_order_acq_rel`.

### <a name="remarks"></a>Примечания

`atomic_store` хранит `Value` в объекте, указанном `Atom`, с соблюдением ограничений `memory_order`, заданных с помощью `Order`.

## <a name="atomic_thread_fence"></a>  atomic_thread_fence

Действует как *граница* — это примитив синхронизации памяти, который обеспечивает порядок между операциями загрузки или сохранения — без связанной атомарной операции.

```cpp
inline void atomic_thread_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

`Order` Объем памяти, упорядочение ограничение, которое определяет тип границы.

### <a name="remarks"></a>Примечания

Аргумент `Order` определяет тип границы.

|||
|-|-|
|`memory_order_relaxed`|Граница не действует.|
|`memory_order_consume`|Граница является границей получения.|
|`memory_order_acquire`|Граница является границей получения.|
|`memory_order_release`|Граница является границей выпуска.|
|`memory_order_acq_rel`|Граница является и границей получения, и границей выпуска.|
|`memory_order_seq_cst`|Граница является и границей получения, и границей выпуска, и она также последовательно согласованная.|

## <a name="kill_dependency"></a>  kill_dependency

Удаляет зависимость.

```cpp
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```

### <a name="parameters"></a>Параметры

`Arg` Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение — `Arg`. Вычисление `Arg` не содержит зависимость для вызова функции. Разбивая возможную цепочку зависимостей, функция позволяет компилятору создавать более эффективный код.

## <a name="see-also"></a>См. также

[\<atomic>](../standard-library/atomic.md)<br/>
