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
ms.openlocfilehash: 6ec4ff879b70e4d2cc16a3328217660db695e859
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377144"
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

*Atom*<br/>
Указатель на *atomic* объект, который хранит значение типа `Ty`.

*Exp*<br/>
Указатель на значение типа `Ty`.

*Значение*<br/>
Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если значения равны; в противном случае **false**.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Exp*<br/>
Указатель на значение типа `Ty`.

*Значение*<br/>
Значение типа `Ty`.

*Order1*<br/>
Первый аргумент [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

*Order2*<br/>
Второй аргумент `memory_order`. Значение *Order2* не может быть `memory_order_release` или `memory_order_acq_rel`, он не может быть надежнее, чем значение *Order1*.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если значения равны; в противном случае **false**.

### <a name="remarks"></a>Примечания

*Атомарная операция сравнения и обмена* сравнивает значение, которое хранится в объекте, который указывает *Atom* со значением, указывает *Exp*. Если значения равны, значение, которое хранится в объекте, который указывает *atom* заменяется *значение* с помощью `read-modify-write` операции и применения ограничений порядка памяти, определяется *Order1*. Если значения не равны, операция заменяет значение, которое указывает *Exp* со значением, которое хранится в объекте, который указывает *Atom* и применяет ограничения порядка памяти, определяется *Order2*.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Exp*<br/>
Указатель на значение типа `Ty`.

*Значение*<br/>
Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если значения равны; в противном случае **false**.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Exp*<br/>
Указатель на значение типа `Ty`.

*Значение*<br/>
Значение типа `Ty`.

*Order1*<br/>
Первый аргумент [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

*Order2*<br/>
Второй аргумент `memory_order`. Значение *Order2* не может быть `memory_order_release` или `memory_order_acq_rel`, не может надежнее, чем значение *Order1*.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если значения равны; в противном случае **false**.

### <a name="remarks"></a>Примечания

Оба сильного и слабого узлов разновидности *атомарная операция сравнения и обмена* гарантии, что они не сохраняют новое значение Если ожидаемое и текущие значения не равны. Надежный flavor гарантирует, что он будет хранить новое значение, если ожидаемый и текущие значения равны. Слабый flavor могут иногда возвращать **false** и не сохранить новое значение, даже если текущий и ожидаемые значения равны. Другими словами, функция возвратит **false**, но может показать последующего изучения ожидаемого значения, который не изменился и таким образом, должно сравнение считаются равными.

## <a name="atomic_exchange"></a>  atomic_exchange

Использует *значение* для замены сохраненного значения *Atom*.

```cpp
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Значение*<br/>
Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Сохраненное значение *Atom* до обмена.

### <a name="remarks"></a>Примечания

`atomic_exchange` Функция выполняет `read-modify-write` операции для обмена значения, которые хранятся в *Atom* с *значение*, с использованием `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_exchange_explicit"></a>  atomic_exchange_explicit

Заменяет сохраненное значение *Atom* с *значение*.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Значение*<br/>
Значение типа `Ty`.

*Порядок*<br/>
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Сохраненное значение *Atom* до обмена.

### <a name="remarks"></a>Примечания

`atomic_exchange_explicit` Функция выполняет `read-modify-write` операции для обмена значения, которые хранятся в *Atom* с *значение*, соблюдением ограничений, которые определяются  *Порядок*.

## <a name="atomic_fetch_add"></a>  atomic_fetch_add

Добавляет значение к существующему значению, хранящемуся в объекте `atomic`.

```cpp
template <class T>
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Atom*<br/>
Указатель на объект `atomic`, который хранит указатель на тип `T`.

*Значение*<br/>
Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

`atomic_fetch_add` Функция выполняет `read-modify-write` операцию, чтобы атомарным образом добавить *значение* к хранимому значению в *Atom*, с использованием `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)ограничение.

Когда атомарным типом является `atomic_address`, *значение* имеет тип `ptrdiff_t` и операция считает сохраненный указатель `char *`.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит указатель на тип `T`.

*Значение*<br/>
Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

`atomic_fetch_add_explicit` Функция выполняет `read-modify-write` операцию, чтобы атомарным образом добавить *значение* к хранимому значению в *Atom*, в пределах [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничения которые заданы `Order`.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*<br/>
Значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

`atomic_fetch_and` Функция выполняет `read-modify-write` операцию, чтобы заменить сохраненное значение *Atom* на результат побитовой операции `and` из *значение* и текущего значения, хранящиеся в *Atom*, с использованием `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничение.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*<br/>
Значение типа `T`.

*Порядок*<br/>
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

`atomic_fetch_and_explicit` Функция выполняет `read-modify-write` операцию, чтобы заменить сохраненное значение *Atom* на результат побитовой операции `and` из *значение* и текущего значения, хранящиеся в *Atom*, соблюдением ограничений, которые определяются *порядок*.

## <a name="atomic_fetch_or"></a>  atomic_fetch_or

Выполняет побитовую операцию `or` со значением и существующим значением, хранящимся в объекте `atomic`.

```cpp
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*<br/>
Значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

`atomic_fetch_or` Функция выполняет `read-modify-write` операцию, чтобы заменить сохраненное значение *Atom* на результат побитовой операции `or` из *значение* и текущего значения, хранящиеся в *Atom*, с использованием `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*<br/>
Значение типа `T`.

*Порядок*<br/>
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

`atomic_fetch_or_explicit` Функция выполняет `read-modify-write` операцию, чтобы заменить сохраненное значение *Atom* на результат побитовой операции `or` из *значение* и текущего значения, хранящиеся в *Atom*, в пределах [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничений *порядок*.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит указатель на тип `T`.

*Значение*<br/>
Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

`atomic_fetch_sub` Функция выполняет `read-modify-write` операцию, чтобы атомарным образом вычесть *значение* из значения, хранящегося в *Atom*, с использованием `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничение.

Когда атомарным типом является `atomic_address`, *значение* имеет тип `ptrdiff_t` и операция считает сохраненный указатель `char *`.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит указатель на тип `T`.

*Значение*<br/>
Значение типа `ptrdiff_t`.

### <a name="return-value"></a>Возвращаемое значение

Значение указателя, содержащегося в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

`atomic_fetch_sub_explicit` Функция выполняет `read-modify-write` операцию, чтобы атомарным образом вычесть *значение* из значения, хранящегося в *Atom*, в пределах [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничения, которые определяются `Order`.

Когда атомарным типом является `atomic_address`, *значение* имеет тип `ptrdiff_t` и операция считает сохраненный указатель `char *`.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*<br/>
Значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

`atomic_fetch_xor` Функция выполняет `read-modify-write` операцию, чтобы заменить сохраненное значение *Atom* на результат побитовой операции `exclusive or` из *значение* и текущего значения, хранящиеся в *Atom*, с использованием `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `T`.

*Значение*<br/>
Значение типа `T`.

*Порядок*<br/>
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащееся в объекте atomic, непосредственно перед выполнением операции.

### <a name="remarks"></a>Примечания

`atomic_fetch_xor_explicit` Функция выполняет `read-modify-write` операцию, чтобы заменить сохраненное значение *Atom* на результат побитовой операции `exclusive or` из *значение* и текущего значения, хранящиеся в *Atom*, в пределах [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничения, которые определяются *порядок*.

## <a name="atomic_flag_clear"></a>  atomic_flag_clear

Наборы **bool** флаг в [atomic_flag](../standard-library/atomic-flag-structure.md) объект **false**, в пределах `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```

### <a name="parameters"></a>Параметры

*Пометить*<br/>
Указатель на объект `atomic_flag` .

## <a name="atomic_flag_clear_explicit"></a>  atomic_flag_clear_explicit

Наборы **bool** флаг в [atomic_flag](../standard-library/atomic-flag-structure.md) объект **false**, в течение указанного [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничения.

```cpp
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Пометить*<br/>
Указатель на объект `atomic_flag` .

*Порядок*<br/>
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_flag_test_and_set"></a>  atomic_flag_test_and_set

Наборы **bool** флаг в [atomic_flag](../standard-library/atomic-flag-structure.md) объект **true**, в пределах ограничений, установленных объектом `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```

### <a name="parameters"></a>Параметры

*Пометить*<br/>
Указатель на объект `atomic_flag` .

### <a name="return-value"></a>Возвращаемое значение

Начальное значение *флаг*.

## <a name="atomic_flag_test_and_set_explicit"></a>  atomic_flag_test_and_set_explicit

Наборы **bool** флаг в [atomic_flag](../standard-library/atomic-flag-structure.md) объект **true**, в течение указанного [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничения.

```cpp
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Пометить*<br/>
Указатель на объект `atomic_flag` .

*Порядок*<br/>
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Возвращаемое значение

Начальное значение *флаг*.

## <a name="atomic_init"></a>  atomic_init

Задает сохраненное значение в объекте `atomic`.

```cpp
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Параметры

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `Ty`.

*Значение*<br/>
Значение типа `Ty`.

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

*Atom*<br/>
Указатель на объект `atomic`, который хранит значение типа `T`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** если атомарные операции с *Atom* без блокировки; в противном случае — значение **false**.

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

*Atom*<br/>
Указатель на объект `atomic`, который содержит значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Извлеченное значение, которое хранится в *Atom*.

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

*Atom*<br/>
Указатель на объект `atomic`, который содержит значение типа `Ty`.

*Порядок*<br/>
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Не используйте `memory_order_release``memory_order_acq_rel`.

### <a name="return-value"></a>Возвращаемое значение

Извлеченное значение, которое хранится в *Atom*.

## <a name="atomic_signal_fence"></a>  atomic_signal_fence

Действует как *граница* — это примитив синхронизации памяти, который обеспечивает порядок между операциями загрузки или сохранения — между другими границами в вызывающем потоке, которые имеют обработчики сигнала, выполняющиеся в одном потоке.

```cpp
inline void atomic_signal_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Порядок*<br/>
Ограничение порядка памяти, которое определяет тип границы.

### <a name="remarks"></a>Примечания

*Порядок* аргумент определяет тип границы.

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

*Atom*<br/>
Указатель на атомарный объект, который содержит значение типа `Ty`.

*Значение*<br/>
Значение типа `Ty`.

### <a name="remarks"></a>Примечания

`atomic_store` хранит *значение* в объект, который указывает *Atom*, в пределах `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ограничение.

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

*Atom*<br/>
Указатель на объект `atomic`, который содержит значение типа `Ty`.

*Значение*<br/>
Значение типа `Ty`.

*Порядок*<br/>
Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Не используйте `memory_order_consume`, `memory_order_acquire` или `memory_order_acq_rel`.

### <a name="remarks"></a>Примечания

`atomic_store` хранит *значение* в объект, который указывает *Atom*, в пределах `memory_order` , указанным параметром *порядок*.

## <a name="atomic_thread_fence"></a>  atomic_thread_fence

Действует как *граница* — это примитив синхронизации памяти, который обеспечивает порядок между операциями загрузки или сохранения — без связанной атомарной операции.

```cpp
inline void atomic_thread_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Параметры

*Порядок*<br/>
Ограничение порядка памяти, которое определяет тип границы.

### <a name="remarks"></a>Примечания

*Порядок* аргумент определяет тип границы.

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

*Arg*<br/>
Значение типа `Ty`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение *Arg*. Вычисление *Arg* не содержит зависимость для вызова функции. Разбивая возможную цепочку зависимостей, функция позволяет компилятору создавать более эффективный код.

## <a name="see-also"></a>См. также

[\<atomic>](../standard-library/atomic.md)<br/>
