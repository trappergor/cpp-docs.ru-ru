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
ms.openlocfilehash: 7308c127bebd2185429509315ebafb3d83a7efea
ms.sourcegitcommit: b0d5557dbb57128da560a0a4634312ec4a050a90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="atomic-structure"></a>Структура atomic

Описывает объект, который выполняет атомарные операции для хранится в виде значения типа *Ty*.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>Участники

|Член|Описание|
|----------|-----------------|
|**Конструктор**||
|[atomic](#atomic)|Создает атомарный объект.|
|**Операторы**||
|[atomic::operator Ty](#op_ty)|Считывает и возвращает сохраненное значение. ([atomic::load](#load))|
|[atomic::operator =](#op_eq)|Использует указанное значение для замены сохраненного значения. ([atomic::store](#store))|
|[atomic::operator ++](#op_inc)|Увеличивает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.|
|[оператор atomic::operator +=](#op_add_eq)|Добавляет указанное значение к сохраненному значению. Используется только специализациями для целочисленных типов и указателей.|
|[atomic::operator--](#op_dec)|Уменьшает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.|
|[atomic::operator-=](#op_sub_eq)|Вычитает указанное значение из сохраненного значения. Используется только специализациями для целочисленных типов и указателей.|
|[atomic::operator & =](#op_and_eq)|Выполняет побитовую операцию и указанное значение и сохраненное значение. Используется только специализациями для целочисленных типов.|
|[atomic::operator&#124;=](#op_or_eq)|Выполняет побитовую операцию или указанное значение и сохраненное значение. Используется только специализациями для целочисленных типов.|
|[atomic::operator ^ =](#op_xor_eq)|Выполняет побитовое исключающее или в указанное значение и сохраненное значение. Используется только специализациями для целочисленных типов.|
|**Функции**||
|[compare_exchange_strong](#compare_exchange_strong)|Выполняет *atomic_compare_and_exchange* операции **это** и возвращает результат.|
|[compare_exchange_weak](#compare_exchange_weak)|Выполняет *weak_atomic_compare_and_exchange* операции **это** и возвращает результат.|
|[fetch_add](#fetch_add)|Добавляет указанное значение к сохраненному значению.|
|[fetch_and](#fetch_and)|Выполняет побитовую операцию и указанное значение и сохраненное значение.|
|[fetch_or](#fetch_or)|Выполняет побитовую операцию или указанное значение и сохраненное значение.|
|[fetch_sub](#fetch_sub)|Вычитает указанное значение из сохраненного значения.|
|[fetch_xor](#fetch_xor)|Выполняет побитовое исключающее или в указанное значение и сохраненное значение.|
|[is_lock_free](#is_lock_free)|Указывает ли атомарных операций с **это** , *блокировки свободного*. Атомарный тип является *неблокирующим*, если никакие атомарные операции с этим типом не используют блокировки.|
|[Нагрузки](#load)|Считывает и возвращает сохраненное значение.|
|[store](#store)|Использует указанное значение для замены сохраненного значения.|

## <a name="remarks"></a>Примечания

Тип *Ty* должно быть *тривиально копируемых*. То есть с использованием [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) для копирования его байтов должен быть допустимым *Ty* объект, который сравнивает его с исходным объектом. [Compare_exchange_weak](#compare_exchange_weak) и [compare_exchange_strong](#compare_exchange_strong) использование функции-члены [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) для определения двух *Ty* значения равны. Эти функции не будет использовать *Ty*-определенные **оператор ==**. Функции-члены **atomic** использовать **memcpy** для копирования значений типа *Ty*.

Частичная специализация **atomic\<Ty \* >** , существует для всех типов указателей. Специализация позволяет добавлять смещение к значению управляемого указателя или вычитать из него смещение. Арифметические операции принимает аргумент типа **ptrdiff_t** и настроить в соответствии с размером этого аргумента *Ty* для согласования с обычным адрес арифметические.

Для любого целочисленного типа, кроме существует специализацию **bool**. Каждая специализация предоставляет широкий набор методов для атомарных арифметических и логических операций.

||||
|-|-|-|
|**atomic\<char >**|**atomic\<подписан char >**|**atomic\<unsigned char >**|
|**atomic\<char16_t >**|**atomic\<char32_t >**|**atomic\<wchar_t >**|
|**atomic\<короткий >**|**atomic\<short без знака >**|**atomic\<int >**|
|**atomic\<unsigned int >**|**atomic\<long >**|**atomic\<unsigned long >**|
|**atomic\<long long >**|**atomic\<long long без знака >**|

Целочисленный специализации являются производными от соответствующего **atomic_integral** типов. Например **atomic\<unsigned int >** является производным от **atomic_uint**.

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

Атомарные объекты не копируются или перемещаются.

Объекты, которые являются атомарными экземпляров\<*Ty*> можно инициализировать только с конструктор, который принимает аргумент типа *Ty* , а не с помощью агрегатной инициализации. Однако объекты atomic_integral можно инициализировать только с помощью агрегатной инициализации.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a> atomic::operator *за этот год*

Оператор для типа, указанного в шаблоне atomic\<*Ty*>. Получает значение, хранимых в  **\*это**.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Примечания

Этот оператор применяется **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_eq"></a> atomic::operator =

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

## <a name="op_inc"></a> atomic::operator ++

Увеличивает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Первые два операторы возвращают Увеличиваемое значение; последние два операторы возвращают значение перед приращение. Используйте операторы **memory_order_seq_cst** [memory_order](atomic-enums.md).

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
Значение целочисленного или указателя.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* объект, содержащий результат сложения.

### <a name="remarks"></a>Примечания

Этот оператор используется **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_dec"></a> atomic::operator--

Уменьшает сохраненное значение. Используется только специализациями для целочисленных типов и указателей.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Первые два операторы возвращают уменьшенное значение; последние два операторы возвращают значение перед декремента. Используйте операторы **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_sub_eq"></a> atomic::operator-=

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
Значение целочисленного или указателя.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* объект, содержащий результат вычитания.

### <a name="remarks"></a>Примечания

Этот оператор используется **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_and_eq"></a> atomic::operator & =

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

Этот оператор выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** с побитовой операции и *значение* и текущие значения, хранящиеся в  **\*это**, в пределах ограничений, наложенных на **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_or_eq"></a> atomic::operator&#124;=

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

Этот оператор выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** с помощью битового оператора или из *значение* и текущие значения, хранящиеся в  **\*это**, в пределах ограничений, наложенных на **memory_order_seq_cst** [memory_order](atomic-enums.md) ограничения.

## <a name="op_xor_eq"></a> atomic::operator ^ =

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

Результат побитовое исключающее или.

### <a name="remarks"></a>Примечания

Этот оператор выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** с побитовое исключающее или для *значение* и текущие значения, хранящиеся в  **\*это**, в пределах ограничений, наложенных на **memory_order_seq_cst** [memory_order](atomic-enums.md) ограничения.

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
Первый аргумент **memory_order**.

*Order2*<br/>
Второй **memory_order** аргумент.

### <a name="return-value"></a>Возвращаемое значение

Объект **bool** , показывающее результат сравнения значений.

### <a name="remarks"></a>Примечания

Это атомарной операции сравнения и обмена сравнивает значение, которое хранится в  **\*это** с *Exp*. Если значения равны, операция заменяет значение, которое хранится в  **\*это** с *значение* , используя операцию чтения, изменения и записи и применяя порядок ограничения памяти, которые заданные *Order1*. Если значения не равны, в операции используется значение, которое хранится в  **\*это** заменить *Exp* и применяет порядок ограничения памяти, которые определяются *Order2* .

Перегрузки, которые не имеют секунды **memory_order** использовать неявную *Order2* , основанный на значении *Order1*. Если *Order1* — **memory_order_acq_rel**, *Order2* — **memory_order_acquire**. Если *Order1* — **memory_order_release**, *Order2* — **memory_order_relaxed**. Во всех остальных случаях *Order2* равен *Order1*.

Для перегрузок, которые принимают два **memory_order** параметров, значение *Order2* не должно быть **memory_order_release** или **memory_order_acq_rel**и не может быть надежнее, чем значение *Order1*.

## <a name="compare_exchange_weak"></a> atomic::compare_exchange_weak

Выполняет слабое atomic сравнение и обмен операцию на  **\*это**.

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
Первый аргумент **memory_order**.

*Order2*<br/>
Второй **memory_order** аргумент.

### <a name="return-value"></a>Возвращаемое значение

Объект **bool** , показывающее результат сравнения значений.

### <a name="remarks"></a>Примечания

Это атомарной операции сравнения и обмена сравнивает значение, которое хранится в  **\*это** с *Exp*. Если значения равны, операция заменяет значение, которое хранится в  **\*это** с*значение* , используя операцию чтения, изменения и записи и применяя порядок ограничения памяти, которые заданные *Order1*. Если значения не равны, в операции используется значение, которое хранится в  **\*это** заменить *Exp* и применяет порядок ограничения памяти, которые определяются *Order2* .

Сравните weak atomic и выполняет операции обмена exchange, если сравниваемые значения равны. Если значения не равны, операция не обязательно выполнять exchange.

Перегрузки, которые не имеют секунды **memory_order** использовать неявную *Order2* , основанный на значении *Order1*. Если *Order1* — **memory_order_acq_rel**, *Order2* — **memory_order_acquire**. Если *Order1* — **memory_order_release**, *Order2* — **memory_order_relaxed**. Во всех остальных случаях *Order2* равен *Order1*.

Для перегрузок, которые принимают два **memory_order** параметров, значение *Order2* не должно быть **memory_order_release** или **memory_order_acq_rel**и не может быть надежнее, чем значение *Order1*.

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
Перечисление **memory_order**.

### <a name="return-value"></a>Возвращаемое значение

Сохраненное значение  **\*это** до exchange.

### <a name="remarks"></a>Примечания

Эта операция не выполняет операции чтения, изменения и записи для использования *значение* заменить значение, которое хранится в  **\*это**, в пределах ограничений памяти, определяемые  *Порядок*.

## <a name="fetch_add"></a> atomic::fetch_add

Получает значение, хранящееся в  **\*это**, а затем добавляет указанное значение с сохраненным значением.

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
Перечисление **memory_order**.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* объект, содержащий значение, хранящееся в  **\*это** перед добавлением.

### <a name="remarks"></a>Примечания

**Fetch_add** метод выполняет чтение изменение запись операцию атомарным образом добавить *значение* с сохраненным значением в  **\*это**и применяет память ограничения, которые определяются *порядок*.

## <a name="fetch_and"></a> atomic::fetch_and

Выполняет побитовую операцию и на значение и существующее значение, которое хранится в  **\*это**.

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
Перечисление **memory_order**.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* объект, содержащий результат битовой операции и.

### <a name="remarks"></a>Примечания

**Fetch_and** метод выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** с побитовой операции и *значение* и текущий значение, хранящееся в  **\*это**, в пределах ограничений памяти, определяемые *порядок*.

## <a name="fetch_or"></a> atomic::fetch_or

Выполняет побитовую операцию или на значение и существующее значение, которое хранится в  **\*это**.

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
Перечисление **memory_order**.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* объект, содержащий результат битовой операции или.

### <a name="remarks"></a>Примечания

**Fetch_or** метод выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** с помощью битового оператора или из *значение* и текущее значение которое хранится в  **\*это**, в пределах ограничений памяти, определяемые *порядок*.

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
Перечисление **memory_order**.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* объект, содержащий результат вычитания.

### <a name="remarks"></a>Примечания

**Fetch_sub** метод выполняет чтение изменение запись операцию Вычитаемый атомарным образом *значение* из значения, хранимые в  **\*это**, в памяти ограничения, которые определяются *порядок*.

## <a name="fetch_xor"></a> atomic::fetch_xor

Выполняет побитовое исключающее или на значение и существующее значение, которое хранится в  **\*это**.

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
Перечисление **memory_order**.

### <a name="return-value"></a>Возвращаемое значение

Объект *Ty* объект, содержащий результат побитовое исключающее или.

### <a name="remarks"></a>Примечания

**Fetch_xor** метод выполняет операцию чтения, изменения и записи, чтобы заменить сохраненное значение  **\*это** с побитовое исключающее или для *значение* и Текущее значение, которое хранится в  **\*это**и применяет ограничения памяти, которые определяются *порядок*.

## <a name="is_lock_free"></a> atomic::is_lock_free

Указывает, является ли атомарных операций с  **\*это** являются блокировки свободного.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

значение true, если атомарные операции над  **\*это** являются блокировки свободного; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Является атомарным типом — блокировка бесплатно, если нет атомарные операции для этого типа используют блокировки.

## <a name="load"></a> atomic::Load

Получает значение, хранимых в  **\*это**, в пределах ограничений заданной памяти.

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
Перечисление **memory_order**. *Порядок* не должно быть **memory_order_release** или **memory_order_acq_rel**.

### <a name="return-value"></a>Возвращаемое значение

Полученное значение, которое хранится в  **\*это**.

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
Объект **memory_order** ограничение.

### <a name="remarks"></a>Примечания

Эта функция-член атомарным образом хранит *значение* в `*this`, в пределах ограничений памяти, определяемые *порядок*.

## <a name="see-also"></a>См. также

[\<atomic>](../standard-library/atomic.md)<br/>
[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
