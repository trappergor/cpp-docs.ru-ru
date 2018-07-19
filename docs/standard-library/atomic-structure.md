---
title: Структура atomic | Документы Майкрософт
ms.custom: ''
ms.date: 04/20/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic
dev_langs:
- C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e5982fc303362a9636c4bf1b0e2d89c6aa05031
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962362"
---
# <a name="atomic-structure"></a>Структура atomic

Описывает объект, который выполняет атомарные операции с сохраненным значением типа *Ty*.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>Участники

|Член|Описание:|
|----------|-----------------|
|**Конструктор**||
|[atomic](#atomic)|Создает атомарный объект.|
|**Операторы**||
|[оператор atomic::operator Ty](#op_ty)|Считывает и возвращает сохраненное значение. ([atomic::load](#load))|
|[оператор atomic::operator =](#op_eq)|Использует указанное значение для замены сохраненного значения. ([atomic::store](#store))|
|[оператор atomic::operator ++](#op_inc)|Увеличивает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.|
|[оператор atomic::operator +=](#op_add_eq)|Добавляет указанное значение к сохраненному значению. Используется только специализациями для целочисленных типов и указателей.|
|[оператор atomic::operator--](#op_dec)|Уменьшает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.|
|[оператор atomic::operator-=](#op_sub_eq)|Вычитает указанное значение из сохраненного значения. Используется только специализациями для целочисленных типов и указателей.|
|[оператор atomic::operator & =](#op_and_eq)|Выполняет побитовую операцию и с указанным значением и сохраненное значение. Используется только специализациями для целочисленных типов.|
|[оператор atomic::operator&#124;=](#op_or_eq)|Выполняет побитовую операцию или с указанным значением и сохраненное значение. Используется только специализациями для целочисленных типов.|
|[оператор atomic::operator ^ =](#op_xor_eq)|Выполняет побитовое исключающее или с указанным значением и сохраненное значение. Используется только специализациями для целочисленных типов.|
|**Функции**||
|[compare_exchange_strong](#compare_exchange_strong)|Выполняет *atomic_compare_and_exchange* операции на **это** и возвращает результат.|
|[compare_exchange_weak](#compare_exchange_weak)|Выполняет *weak_atomic_compare_and_exchange* операции на **это** и возвращает результат.|
|[fetch_add](#fetch_add)|Добавляет указанное значение к сохраненному значению.|
|[fetch_and](#fetch_and)|Выполняет побитовую операцию и с указанным значением и сохраненное значение.|
|[fetch_or](#fetch_or)|Выполняет побитовую операцию или с указанным значением и сохраненное значение.|
|[fetch_sub](#fetch_sub)|Вычитает указанное значение из сохраненного значения.|
|[fetch_xor](#fetch_xor)|Выполняет побитовое исключающее или с указанным значением и сохраненное значение.|
|[is_lock_free](#is_lock_free)|Указывает, является ли атомарные операции с **это** являются *без блокировки*. Атомарный тип является *неблокирующим*, если никакие атомарные операции с этим типом не используют блокировки.|
|[загрузить](#load)|Считывает и возвращает сохраненное значение.|
|[store](#store)|Использует указанное значение для замены сохраненного значения.|

## <a name="remarks"></a>Примечания

Тип *Ty* должно быть *тривиально копируемых*. То есть с помощью [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) для копирования его байтов должен создаваться допустимый *Ty* объект, равный исходному объекту. [Compare_exchange_weak](#compare_exchange_weak) и [compare_exchange_strong](#compare_exchange_strong) использование функции-члены [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) для определения двух *Ty* значения равны. Эти функции не будут использовать *Ty*-определенные `operator==`. Функции-члены `atomic` использовать `memcpy` для копирования значений типа *Ty*.

Частичная специализация **atomic\<Ty \* >** , существует для всех типов указателей. Специализация позволяет добавлять смещение к значению управляемого указателя или вычитать из него смещение. Арифметические операции принимают аргумент типа `ptrdiff_t` и настраивают этот аргумент в соответствии с размером *Ty* для согласования с обычным вычислением адресов.

Специализация существует для любого целочисленного типа, за исключением **bool**. Каждая специализация предоставляет широкий набор методов для атомарных арифметических и логических операций.

||||
|-|-|-|
|**atomic\<char >**|**atomic\<автоматический char >**|**atomic\<unsigned char >**|
|**atomic\<char16_t >**|**atomic\<char32_t >**|**atomic\<wchar_t >**|
|**atomic\<короткий >**|**atomic\<unsigned short >**|**atomic\<int >**|
|**atomic\<unsigned int >**|**atomic\<long >**|**atomic\<unsigned long >**|
|**atomic\<long long >**|**atomic\<long long без знака >**|

Специализации для целочисленных типов являются производными от соответствующих типов `atomic_integral`. Например **atomic\<unsigned int >** является производным от `atomic_uint`.

## <a name="requirements"></a>Требования

**Заголовок:** \<atomic >

**Пространство имен:** std

## <a name="atomic"></a> atomic::atomic

Создает атомарный объект.

```cpp
atomic();
atomic( const atomic& );
atomic( Ty Value ) noexcept;
```

### <a name="parameters"></a>Параметры

*Значение*<br/>
Значение инициализации.

### <a name="remarks"></a>Примечания

Атомарные объекты нельзя копировать или перемещать.

Объекты, которые являются экземпляров атомарных\<*Ty*> можно инициализировать только с помощью конструктора, который принимает аргумент типа *Ty* и не с помощью агрегатной инициализации. Тем не менее объекты atomic_integral можно инициализировать только с помощью агрегатной инициализации.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a> оператор atomic::operator *за этот год*

Оператор для типа, указанного в шаблоне, атомарные\<*Ty*>. Извлекает сохраненное значение в  **\*это**.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Примечания

Этот оператор применяется `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_eq"></a> оператор atomic::operator =

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

*Значение*<br/>
Объект *Ty* объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает *значение*.

## <a name="op_inc"></a> оператор atomic::operator ++

Увеличивает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Первые два операторы возвращают увеличенное значение; последние два операторы возвращают значение до увеличения значения. Используйте операторы `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_add_eq"></a> оператор atomic::operator +=

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

*Значение*<br/>
Целочисленный тип или указатель на значение.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий результат сложения.

### <a name="remarks"></a>Примечания

Этот оператор использует `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_dec"></a> оператор atomic::operator--

Уменьшает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Первые два операторы возвращают уменьшенное значение; последние два операторы возвращают значение до уменьшения значения. Используйте операторы `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_sub_eq"></a> оператор atomic::operator-=

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

*Значение*<br/>
Целочисленный тип или указатель на значение.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* объект, который содержит результат вычитания.

### <a name="remarks"></a>Примечания

Этот оператор использует `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_and_eq"></a> оператор atomic::operator & =

Выполняет побитовую операцию и на указанное значение и сохраненное значение  **\*это**. Используется только специализациями для целочисленных типов.

```cpp
atomic<Ty>::operator&= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator&= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значение*<br/>
Значение типа *Ty*.

### <a name="return-value"></a>Возвращаемое значение

Результат битовой операции и.

### <a name="remarks"></a>Примечания

Этот оператор выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** на результат побитовой операции и из *значение* и текущего значения, хранящиеся в  **\*это**, в пределах ограничений, установленных объектом `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_or_eq"></a> оператор atomic::operator&#124;=

Выполняет побитовую операцию или на указанное значение и сохраненное значение  **\*это**. Используется только специализациями для целочисленных типов.

```cpp
atomic<Ty>::operator|= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator|= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значение*<br/>
Значение типа *Ty*.

### <a name="return-value"></a>Возвращаемое значение

Результат битовой операции или.

### <a name="remarks"></a>Примечания

Этот оператор выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** с побитовым объектом или объектом *значение* и текущего значения, хранящиеся в  **\*это**, в пределах ограничений, установленных объектом `memory_order_seq_cst` [memory_order](atomic-enums.md) ограничения.

## <a name="op_xor_eq"></a> оператор atomic::operator ^ =

Выполняет побитовое исключающее или на указанное значение и сохраненное значение  **\*это**. Используется только специализациями для целочисленных типов.

```cpp
atomic<Ty>::operator^= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator^= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Параметры

*Значение*<br/>
Значение типа *Ty*.

### <a name="return-value"></a>Возвращаемое значение

Результат побитового исключающего или.

### <a name="remarks"></a>Примечания

Этот оператор выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** с побитового исключающего или *значение* и текущего значения, хранящиеся в  **\*это**, в пределах ограничений, установленных объектом `memory_order_seq_cst` [memory_order](atomic-enums.md) ограничения.

## <a name="compare_exchange_strong"></a> atomic::compare_exchange_strong

Выполняет атомарную операцию сравнения и обмена на  **\*это**.

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

*Exp*<br/>
Значение типа *Ty*.

*Значение*<br/>
Значение типа *Ty*.

*Order1*<br/>
Первый `memory_order` аргумент.

*Order2*<br/>
Второй аргумент `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект **bool** , определяющий результат сравнения значений.

### <a name="remarks"></a>Примечания

Это атомарная операция сравнения и обмена сравнивает значение, которое хранится в  **\*это** с *Exp*. Если значения равны, операция заменяет значение, которое хранится в  **\*это** с *значение* с помощью операции чтения, изменения и записи и применения ограничений порядка памяти, определяется *Order1*. Если значения не равны, операция использует значение, которое хранится в  **\*это** для замены *Exp* и применяет ограничения порядка памяти, которые определяются *Order2* .

Перегрузки, которые не имеют секунды `memory_order` использовать неявный *Order2* , основанный на значении *Order1*. Если *Order1* — `memory_order_acq_rel`, *Order2* является `memory_order_acquire`. Если *Order1* — `memory_order_release`, *Order2* является `memory_order_relaxed`. Во всех остальных случаях *Order2* равен *Order1*.

Для перегрузок, которые принимают два `memory_order` параметры, значение *Order2* не должно быть `memory_order_release` или `memory_order_acq_rel`и не может быть надежнее, чем значение *Order1*.

## <a name="compare_exchange_weak"></a> atomic::compare_exchange_weak

Выполняет слабые атомарная операция сравнения и обмена  **\*это**.

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

*Exp*<br/>
Значение типа *Ty*.

*Значение*<br/>
Значение типа *Ty*.

*Order1*<br/>
Первый `memory_order` аргумент.

*Order2*<br/>
Второй аргумент `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект **bool** , определяющий результат сравнения значений.

### <a name="remarks"></a>Примечания

Это атомарная операция сравнения и обмена сравнивает значение, которое хранится в  **\*это** с *Exp*. Если значения равны, операция заменяет значение, которое хранится в  **\*это** с*значение* с помощью операции чтения, изменения и записи и применения ограничений порядка памяти, определяется *Order1*. Если значения не равны, операция использует значение, которое хранится в  **\*это** для замены *Exp* и применяет ограничения порядка памяти, которые определяются *Order2* .

Сравните слабую атомарную и операции обмена выполняет обмен, если сравниваемые значения равны. Если значения не равны, операция необязательно выполнит обмен.

Перегрузки, которые не имеют секунды `memory_order` использовать неявный *Order2* , основанный на значении *Order1*. Если *Order1* — `memory_order_acq_rel`, *Order2* является `memory_order_acquire`. Если *Order1* — `memory_order_release`, *Order2* является `memory_order_relaxed`. Во всех остальных случаях *Order2* равен *Order1*.

Для перегрузок, которые принимают два `memory_order` параметры, значение *Order2* не должно быть `memory_order_release` или `memory_order_acq_rel`и не может быть надежнее, чем значение *Order1*.

## <a name="exchange"></a> atomic::Exchange

Использует указанное значение для замены сохраненного значения  **\*это**.

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

*Значение*<br/>
Значение типа *Ty*.

*Порядок*<br/>
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Сохраненное значение  **\*это** до обмена.

### <a name="remarks"></a>Примечания

Эта операция выполняет операцию чтения, изменения и записи, чтобы использовать *значение* заменить значение, которое хранится в  **\*это**, соблюдением ограничений, которые определяются  *Порядок*.

## <a name="fetch_add"></a> atomic::fetch_add

Получает значение, хранящееся в  **\*это**, а затем добавляет указанное значение к сохраненному значению.

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

*Значение*<br/>
Значение типа *Ty*.

*Порядок*<br/>
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий значение, хранящееся в  **\*это** перед добавлением.

### <a name="remarks"></a>Примечания

`fetch_add` Метод выполняет операцию чтения, изменения и записи, чтобы атомарным образом добавить *значение* к хранимому значению в  **\*это**и применяет ограничения памяти, которые определяются *Порядок*.

## <a name="fetch_and"></a> atomic::fetch_and

Выполняет побитовую операцию и на значением и существующим значением, хранится в  **\*это**.

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

*Значение*<br/>
Значение типа *Ty*.

*Порядок*<br/>
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий результат битовой операции и.

### <a name="remarks"></a>Примечания

`fetch_and` Метод выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** на результат побитовой операции и из *значение* и текущего значения, хранящиеся в  **\*это**, соблюдением ограничений, которые определяются *порядок*.

## <a name="fetch_or"></a> atomic::fetch_or

Выполняет побитовую операцию или на значение и существующим значением, хранящийся в  **\*это**.

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

*Значение*<br/>
Значение типа *Ty*.

*Порядок*<br/>
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий результат битовой операции или.

### <a name="remarks"></a>Примечания

`fetch_or` Метод выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** с побитовым объектом или объектом *значение* и текущего значения, хранящиеся в  **\*это**, соблюдением ограничений, которые определяются *порядок*.

## <a name="fetch_sub"></a> atomic::fetch_sub

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

*Значение*<br/>
Значение типа *Ty*.

*Порядок*<br/>
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* объект, который содержит результат вычитания.

### <a name="remarks"></a>Примечания

`fetch_sub` Метод выполняет операцию чтения, изменения и записи, чтобы атомарным образом вычесть *значение* из значения, хранящегося в  **\*это**, соблюдением ограничений, которые определяются *Порядок*.

## <a name="fetch_xor"></a> atomic::fetch_xor

Выполняет побитовое исключающее или на значение и существующим значением, хранящийся в  **\*это**.

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

*Значение*<br/>
Значение типа *Ty*.

*Порядок*<br/>
Объект `memory_order`.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* , содержащий результат побитового исключающего или.

### <a name="remarks"></a>Примечания

`fetch_xor` Метод выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** с побитового исключающего или *значение* и текущего значения, хранящиеся в  **\*это**и применяет ограничения памяти, которые определяются *порядок*.

## <a name="is_lock_free"></a> atomic::is_lock_free

Указывает ли атомарные операции с  **\*это** являются без блокировки.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

значение true, если атомарные операции с  **\*это** являются блокировки бесплатно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Атомарный тип является неблокирующим, если никакие атомарные операции с этим типом не используют блокировки.

## <a name="load"></a> atomic::Load

Извлекает сохраненное значение в  **\*это**, в пределах указанной области памяти ограничений.

```cpp
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const volatile noexcept;
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const noexcept;
```

### <a name="parameters"></a>Параметры

*Порядок*<br/>
Объект `memory_order`. *Порядок* не должно быть `memory_order_release` или `memory_order_acq_rel`.

### <a name="return-value"></a>Возвращаемое значение

Извлеченное значение, которое хранится в  **\*это**.

## <a name="store"></a> atomic::Store

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

*Значение*<br/>
Объект *Ty* объекта.

*Порядок*<br/>
Объект `memory_order` ограничение.

### <a name="remarks"></a>Примечания

Эта функция-член атомарно сохраняет *значение* в `*this`, соблюдением ограничений, которые определяются *порядок*.

## <a name="see-also"></a>См. также

[\<atomic>](../standard-library/atomic.md)<br/>
[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
