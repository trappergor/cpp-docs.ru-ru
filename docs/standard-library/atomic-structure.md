---
title: Структура atomic
ms.date: 04/20/2018
f1_keywords:
- atomic/std::atomic
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
ms.openlocfilehash: 8701078f8a034d80dae41eee0d842fb15fd8d3a4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203940"
---
# <a name="atomic-structure"></a>Структура atomic

Описывает объект, выполняющий атомарные операции с сохраненным значением типа *Ty*.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>Участники

|Член|Описание|
|----------|-----------------|
|**Конструктор**||
|[атомарная](#atomic)|Создает атомарный объект.|
|**Операторы**||
|[Атомарный:: operator Ty](#op_ty)|Считывает и возвращает сохраненное значение. ([атомарный:: Load](#load))|
|[Атомарный:: operator =](#op_eq)|Использует указанное значение для замены сохраненного значения. ([Atomic:: Store](#store))|
|[атомарные:: operator + +](#op_inc)|Увеличивает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.|
|[атомарные:: operator + =](#op_add_eq)|Добавляет указанное значение к сохраненному значению. Используется только специализациями для целочисленных типов и указателей.|
|[Атомарный:: operator--](#op_dec)|Уменьшает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.|
|[Атомарный:: operator-=](#op_sub_eq)|Вычитает указанное значение из сохраненного значения. Используется только специализациями для целочисленных типов и указателей.|
|[Атомарный:: operator&=](#op_and_eq)|Выполняет операцию побитового и для указанного значения и сохраненного значения. Используется только специализациями для целочисленных типов.|
|[Атомарный:: operator&#124;=](#op_or_eq)|Выполняет операцию побитового или для указанного значения и сохраненного значения. Используется только специализациями для целочисленных типов.|
|[Атомарный:: operator ^ =](#op_xor_eq)|Выполняет операцию побитового исключающего или для указанного значения и сохраненного значения. Используется только специализациями для целочисленных типов.|
|**Функции**||
|[compare_exchange_strong](#compare_exchange_strong)|Выполняет *atomic_compare_and_exchange* операцию над **`this`** и возвращает результат.|
|[compare_exchange_weak](#compare_exchange_weak)|Выполняет *weak_atomic_compare_and_exchange* операцию над **`this`** и возвращает результат.|
|[fetch_add](#fetch_add)|Добавляет указанное значение к сохраненному значению.|
|[fetch_and](#fetch_and)|Выполняет операцию побитового и для указанного значения и сохраненного значения.|
|[fetch_or](#fetch_or)|Выполняет операцию побитового или для указанного значения и сохраненного значения.|
|[fetch_sub](#fetch_sub)|Вычитает указанное значение из сохраненного значения.|
|[fetch_xor](#fetch_xor)|Выполняет операцию побитового исключающего или для указанного значения и сохраненного значения.|
|[is_lock_free](#is_lock_free)|Указывает, будут ли атомарные операции для **`this`** *блокироваться бесплатно*. Атомарный тип является *неблокирующим*, если никакие атомарные операции с этим типом не используют блокировки.|
|[загрузка](#load)|Считывает и возвращает сохраненное значение.|
|[хранение](#store)|Использует указанное значение для замены сохраненного значения.|

## <a name="remarks"></a>Remarks

Тип *Ty* должен быть *простым копированием*. То есть при использовании [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) для копирования байтов необходимо создать допустимый объект *Ty* , который сравнивается с исходным объектом. Функции члена [compare_exchange_weak](#compare_exchange_weak) и [compare_exchange_strong](#compare_exchange_strong) используют [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) для определения того, равны ли два значения *Ty* . Эти функции не будут использовать определенную *Ty* `operator==` . Функции элементов, `atomic` используемые `memcpy` для копирования значений типа *Ty*.

Частичная специализация, **атомарная \<Ty \*> **, существует для всех типов указателей. Специализация позволяет добавлять смещение к значению управляемого указателя или вычитать из него смещение. Арифметические операции принимают аргумент типа `ptrdiff_t` и корректируют этот аргумент в соответствии с размером *Ty* , который должен быть согласован с обычной арифметикой адресов.

Для каждого целочисленного типа существует специализация, за исключением **`bool`** . Каждая специализация предоставляет широкий набор методов для атомарных арифметических и логических операций.

||||
|-|-|-|
|**атомарная\<char>**|**атомарная\<signed char>**|**атомарная\<unsigned char>**|
|**атомарная\<char16_t>**|**атомарная\<char32_t>**|**атомарная\<wchar_t>**|
|**атомарная\<short>**|**атомарная\<unsigned short>**|**атомарная\<int>**|
|**атомарная\<unsigned int>**|**атомарная\<long>**|**атомарная\<unsigned long>**|
|**атомарная\<long long>**|**атомарная\<unsigned long long>**|

Специализации для целочисленных типов являются производными от соответствующих типов `atomic_integral`. Например, **атомарный \<unsigned int> ** является производным от `atomic_uint` .

## <a name="requirements"></a>Требования

**Заголовок:**\<atomic>

**Пространство имен:** std

## <a name="atomicatomic"></a><a name="atomic"></a>Атомарная:: Atomic

Создает атомарный объект.

```cpp
atomic();
atomic( const atomic& );
atomic( Ty Value ) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Значение инициализации.

### <a name="remarks"></a>Remarks

Атомарные объекты не могут быть скопированы или перемещены.

Объекты, являющиеся экземплярами Atomic, \<*Ty*> могут быть инициализированы только конструктором, который принимает аргумент типа *Ty* , а не с помощью агрегатной инициализации. Однако atomic_integral объекты можно инициализировать только с помощью агрегатной инициализации.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="atomicoperator-ty"></a><a name="op_ty"></a>Атомарный:: operator *Ty*

Оператор для типа, указанного в шаблоне, Atomic \<*Ty*> . Извлекает сохраненное значение в ** \* этом**.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Remarks

Этот оператор применяет `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="atomicoperator"></a><a name="op_eq"></a>Атомарный:: operator =

Сохраняет указанное значение.

```cpp
Ty operator=(
   Ty Value
) volatile noexcept;
Ty operator=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Объект *Ty* .

### <a name="return-value"></a>Возвращаемое значение

Возвращает *значение*.

## <a name="atomicoperator"></a><a name="op_inc"></a>атомарные:: operator + +

Увеличивает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Первые два оператора возвращают значение с приращением; последние два оператора возвращают значение до приращения. Операторы используют `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="atomicoperator"></a><a name="op_add_eq"></a>атомарные:: operator + =

Добавляет указанное значение к сохраненному значению. Используется только специализациями для целочисленных типов и указателей.

```cpp
Ty atomic<Ty>::operator+=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator+=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Целочисленное значение или.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий результат сложения.

### <a name="remarks"></a>Remarks

Этот оператор использует `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="atomicoperator--"></a><a name="op_dec"></a>Атомарный:: operator--

Уменьшает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Первые два оператора возвращают уменьшенное значение; последние два оператора возвращают значение до декремента. Операторы используют `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="atomicoperator-"></a><a name="op_sub_eq"></a>Атомарный:: operator-=

Вычитает указанное значение из сохраненного значения. Используется только специализациями для целочисленных типов и указателей.

```cpp
Ty atomic<Ty>::operator-=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator-=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Целочисленное значение или.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий результат вычитания.

### <a name="remarks"></a>Remarks

Этот оператор использует `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="atomicoperator"></a><a name="op_and_eq"></a>Атомарный:: operator&=

Выполняет операцию побитового и для указанного значения и сохраненного значения ** \* этого**объекта. Используется только специализациями для целочисленных типов.

```cpp
atomic<Ty>::operator&= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator&= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Значение типа *Ty*.

### <a name="return-value"></a>Возвращаемое значение

Результат побитового и.

### <a name="remarks"></a>Remarks

Этот оператор выполняет операцию чтения и изменения записи, чтобы заменить сохраненное значение ** \* этого** параметра на побитовое и для *значения* , а также текущее значение, хранящееся в ** \* этом**объекте, в пределах ограничений `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="atomicoperator124"></a><a name="op_or_eq"></a>Атомарный:: operator&#124;=

Выполняет операцию побитового или для указанного значения и сохраненного значения ** \* этого**объекта. Используется только специализациями для целочисленных типов.

```cpp
atomic<Ty>::operator|= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator|= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Значение типа *Ty*.

### <a name="return-value"></a>Возвращаемое значение

Результат побитового или.

### <a name="remarks"></a>Remarks

Этот оператор выполняет операцию чтения и изменения записи, чтобы заменить сохраненное значение ** \* этого** параметра на побитовое или для *значения* , а также текущее значение, хранящееся в ** \* этом**объекте, в пределах ограничений `memory_order_seq_cst` [memory_orderных](atomic-enums.md) ограничений.

## <a name="atomicoperator"></a><a name="op_xor_eq"></a>Атомарный:: operator ^ =

Выполняет операцию побитового исключающего или для указанного значения и сохраненного значения ** \* этого**объекта. Используется только специализациями для целочисленных типов.

```cpp
atomic<Ty>::operator^= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator^= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Значение типа *Ty*.

### <a name="return-value"></a>Возвращаемое значение

Результат побитового исключающего или.

### <a name="remarks"></a>Remarks

Этот оператор выполняет операцию чтения-изменения-записи, чтобы заменить сохраненное значение ** \* этого** параметра на побитовое исключающее или для *значения* , а также текущее значение, хранящееся в ** \* этом**объекте, в пределах ограничений `memory_order_seq_cst` [memory_orderных](atomic-enums.md) ограничений.

## <a name="atomiccompare_exchange_strong"></a><a name="compare_exchange_strong"></a>ATOMIC:: compare_exchange_strong

Выполняет атомарную операцию сравнения и обмена для ** \* этого**.

```cpp
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Параметры

*Расширением*\
Значение типа *Ty*.

*Значений*\
Значение типа *Ty*.

*Order1*\
Первый `memory_order` аргумент.

*Order2*\
Второй аргумент `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Значение типа **`bool`** , указывающее результат сравнения значений.

### <a name="remarks"></a>Remarks

Эта операция атомарных операций сравнения и обмена сравнивает значение, хранящееся в ** \* этом** параметре, с *exp*. Если значения равны, операция заменяет значение, хранящееся в ** \* этом** *значении* , на значение с помощью операции чтения и изменения, а также применяет ограничения порядка памяти, заданные параметром *Order1*. Если значения не равны, операция использует значение, хранящееся в ** \* этом** параметре, для замены *exp* и применяет ограничения порядка памяти, заданные параметром *Order2*.

Перегрузки, не имеющие второй, `memory_order` используют неявный *Order2* , основанный на значении *Order1*. Если *Order1* имеет значение `memory_order_acq_rel` , *Order2* имеет значение `memory_order_acquire` . Если *Order1* имеет значение `memory_order_release` , *Order2* имеет значение `memory_order_relaxed` . Во всех остальных случаях *Order2* равно *Order1*.

Для перегрузок, принимающих два `memory_order` параметра, значение *Order2* не должно быть `memory_order_release` или `memory_order_acq_rel` , а также не должно быть надежным, чем значение *Order1*.

## <a name="atomiccompare_exchange_weak"></a><a name="compare_exchange_weak"></a>ATOMIC:: compare_exchange_weak

Выполняет слабую атомарную операцию сравнения и обмена для ** \* этого**.

```cpp
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Параметры

*Расширением*\
Значение типа *Ty*.

*Значений*\
Значение типа *Ty*.

*Order1*\
Первый `memory_order` аргумент.

*Order2*\
Второй аргумент `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Значение типа **`bool`** , указывающее результат сравнения значений.

### <a name="remarks"></a>Remarks

Эта операция атомарных операций сравнения и обмена сравнивает значение, хранящееся в ** \* этом** параметре, с *exp*. Если значения равны, операция заменяет значение, хранящееся в ** \* этом** *значении* , на значение с помощью операции чтения и изменения, а также применяет ограничения порядка памяти, заданные параметром *Order1*. Если значения не равны, операция использует значение, хранящееся в ** \* этом** параметре, для замены *exp* и применяет ограничения порядка памяти, заданные параметром *Order2*.

Слабая атомарная операция сравнения и обмена выполняет обмен, если сравниваемые значения равны. Если значения не равны, операция не гарантирует выполнение Exchange.

Перегрузки, не имеющие второй, `memory_order` используют неявный *Order2* , основанный на значении *Order1*. Если *Order1* имеет значение `memory_order_acq_rel` , *Order2* имеет значение `memory_order_acquire` . Если *Order1* имеет значение `memory_order_release` , *Order2* имеет значение `memory_order_relaxed` . Во всех остальных случаях *Order2* равно *Order1*.

Для перегрузок, принимающих два `memory_order` параметра, значение *Order2* не должно быть `memory_order_release` или `memory_order_acq_rel` , а также не должно быть надежным, чем значение *Order1*.

## <a name="atomicexchange"></a><a name="exchange"></a>атомарные:: Exchange

Использует указанное значение для замены сохраненного значения ** \* this**.

```cpp
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Значение типа *Ty*.

*Порядок*\
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Сохраненное значение ** \* этого** объекта перед обменом.

### <a name="remarks"></a>Remarks

Эта операция выполняет операцию чтения, изменения и записи, чтобы использовать *значение* для замены значения, хранящегося в ** \* этом**объекте, в пределах ограничений памяти, заданных по *порядку*.

## <a name="atomicfetch_add"></a><a name="fetch_add"></a>ATOMIC:: fetch_add

Извлекает значение, хранящееся в ** \* этом**элементе, а затем добавляет указанное значение к сохраненному значению.

```cpp
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Значение типа *Ty*.

*Порядок*\
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий значение, ** \* хранящееся перед** добавлением.

### <a name="remarks"></a>Remarks

`fetch_add`Метод выполняет операцию чтения-изменения и записи для атомарного добавления *значения* к сохраненному значению в ** \* этом**и применяет ограничения памяти, заданные по *порядку*.

## <a name="atomicfetch_and"></a><a name="fetch_and"></a>ATOMIC:: fetch_and

Выполняет операцию побитового и для значения и существующего значения, хранящегося в ** \* этом**.

```cpp
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Значение типа *Ty*.

*Порядок*\
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий результат побитового и.

### <a name="remarks"></a>Remarks

`fetch_and`Метод выполняет операцию чтения-изменения и записи, чтобы заменить сохраненное значение ** \* этого** параметра на побитовое и для *значения* , а также текущее значение, хранящееся в ** \* этом**объекте, в пределах ограничений памяти, заданных по *порядку*.

## <a name="atomicfetch_or"></a><a name="fetch_or"></a>ATOMIC:: fetch_or

Выполняет операцию побитового или для значения и существующего значения, хранящегося в ** \* этом**.

```cpp
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Значение типа *Ty*.

*Порядок*\
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий результат побитового или.

### <a name="remarks"></a>Remarks

`fetch_or`Метод выполняет операцию чтения-изменения и записи для замены сохраненного значения ** \* этого** параметра на побитовое или для *значения* , а также текущего значения, хранящегося в ** \* этом**объекте, в пределах ограничений памяти, заданных по *порядку*.

## <a name="atomicfetch_sub"></a><a name="fetch_sub"></a>ATOMIC:: fetch_sub

Вычитает указанное значение из сохраненного значения.

```cpp
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Значение типа *Ty*.

*Порядок*\
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий результат вычитания.

### <a name="remarks"></a>Remarks

`fetch_sub`Метод выполняет операцию чтения-изменения и записи для атомарного вычитания *значения* из сохраненного значения в рамках ** \* **ограничений памяти, заданных по *порядку*.

## <a name="atomicfetch_xor"></a><a name="fetch_xor"></a>ATOMIC:: fetch_xor

Выполняет операцию побитового исключающего или для значения и существующего значения, хранящегося в ** \* этом**.

```cpp
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Значение типа *Ty*.

*Порядок*\
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий результат побитового исключающего или.

### <a name="remarks"></a>Remarks

`fetch_xor`Метод выполняет операцию чтения и изменения записи, чтобы заменить сохраненное значение ** \* этого** параметра на побитовое исключающее или для *значения* , а также текущее значение, хранящееся в ** \* этом**элементе, и применяет ограничения памяти, заданные по *порядку*.

## <a name="atomicis_lock_free"></a><a name="is_lock_free"></a>ATOMIC:: is_lock_free

Указывает, являются ли атомарные операции с ** \* этой** блокировкой свободными.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

значение true, если атомарные операции на ** \* этом** блоке являются свободными. в противном случае — значение false.

### <a name="remarks"></a>Remarks

Атомарный тип является неблокирующим, если никакие атомарные операции с этим типом не используют блокировки.

## <a name="atomicload"></a><a name="load"></a>Атомарный:: Load

Извлекает сохраненное ** \* значение в пределах**указанных ограничений памяти.

```cpp
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const volatile noexcept;
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const noexcept;
```

### <a name="parameters"></a>Параметры

*Порядок*\
Объект `memory_order`. *Порядок* не должен быть `memory_order_release` или `memory_order_acq_rel` .

### <a name="return-value"></a>Возвращаемое значение

Извлеченное значение, хранящееся в ** \* этом**.

## <a name="atomicstore"></a><a name="store"></a>ATOMIC:: Store

Сохраняет указанное значение.

```cpp
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значений*\
Объект *Ty* .

*Порядок*\
`memory_order`Ограничение.

### <a name="remarks"></a>Remarks

Эта функция члена атомарно сохраняет *значение* в **`*this`** , в пределах ограничений памяти, заданных по *порядку*.

## <a name="see-also"></a>См. также раздел

[\<atomic>](../standard-library/atomic.md)\
[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
