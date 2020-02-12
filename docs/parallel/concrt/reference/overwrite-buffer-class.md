---
title: Класс overwrite_buffer
ms.date: 11/04/2016
f1_keywords:
- overwrite_buffer
- AGENTS/concurrency::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::has_value
- AGENTS/concurrency::overwrite_buffer::value
- AGENTS/concurrency::overwrite_buffer::accept_message
- AGENTS/concurrency::overwrite_buffer::consume_message
- AGENTS/concurrency::overwrite_buffer::link_target_notification
- AGENTS/concurrency::overwrite_buffer::propagate_message
- AGENTS/concurrency::overwrite_buffer::propagate_to_any_targets
- AGENTS/concurrency::overwrite_buffer::release_message
- AGENTS/concurrency::overwrite_buffer::reserve_message
- AGENTS/concurrency::overwrite_buffer::resume_propagation
- AGENTS/concurrency::overwrite_buffer::send_message
- AGENTS/concurrency::overwrite_buffer::supports_anonymous_source
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
ms.openlocfilehash: 5b222170112f43ae9700054f42e1368545612d00
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138797"
---
# <a name="overwrite_buffer-class"></a>Класс overwrite_buffer

Блок обмена сообщениями `overwrite_buffer` — это упорядоченный блок `propagator_block` с несколькими источниками и несколькими целями, который может хранить одно сообщение в один момент времени. Новые сообщения перезаписывают предыдущие.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных сообщений, хранимых и распространяемых буфером.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[overwrite_buffer](#ctor)|Перегружен. Конструирует блок сообщений `overwrite_buffer`.|
|[Деструктор ~ overwrite_buffer](#dtor)|Уничтожает блок сообщений `overwrite_buffer`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[has_value](#has_value)|Проверяет, имеет ли этот блок сообщений `overwrite_buffer` значение.|
|[value](#value)|Возвращает ссылку на текущие полезные данные сообщения, хранящегося в блоке сообщений `overwrite_buffer`.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[accept_message](#accept_message)|Принимает сообщение, предложенное этим блоком сообщений `overwrite_buffer`, возвращая копию сообщения вызывающему.|
|[consume_message](#consume_message)|Использует сообщение, которое было ранее предложено блоком `overwrite_buffer` Messaging, и зарезервировано целевым объектом, возвращая копию сообщения вызывающему объекту.|
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим блоком сообщений `overwrite_buffer`.|
|[propagate_message](#propagate_message)|Асинхронно передает сообщение из блока `ISource` в этот `overwrite_buffer` блок сообщений. Вызывается методом `propagate` при вызове из исходного блока.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Помещает `message _PMessage` в этом `overwrite_buffer` блоке обмена сообщениями и предлагает его всем связанным целевым объектам.|
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Резервирует сообщение, которое было предложено этим блоком `overwrite_buffer` Messaging. (Переопределяет [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Возобновляет распространение после освобождения резервирования. (Переопределяет [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Синхронно передает сообщение из блока `ISource` в этот `overwrite_buffer` блок сообщений. Вызывается методом `send` при вызове из исходного блока.|
|[supports_anonymous_source](#supports_anonymous_source)|Переопределяет метод `supports_anonymous_source`, чтобы указать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником. (Переопределяет метод [ITarget:: supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

## <a name="remarks"></a>Remarks

Блок обмена сообщениями `overwrite_buffer` распространяет копии сохраненного сообщения каждому из его целевых объектов.

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`overwrite_buffer`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept_message"></a>accept_message

Принимает сообщение, предложенное этим блоком сообщений `overwrite_buffer`, возвращая копию сообщения вызывающему.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` предлагаемого `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `message`, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Remarks

Блок обмена сообщениями `overwrite_buffer` возвращает копии сообщения в целевые объекты, вместо того чтобы передавать владение текущим сообщением.

## <a name="consume_message"></a>consume_message

Использует сообщение, которое было ранее предложено блоком `overwrite_buffer` Messaging, и зарезервировано целевым объектом, возвращая копию сообщения вызывающему объекту.

```cpp
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` используемого объекта `message`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `message`, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Remarks

Аналогично `accept`, но всегда предшествует вызов `reserve`.

## <a name="has_value"></a>has_value

Проверяет, имеет ли этот блок сообщений `overwrite_buffer` значение.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если блок получил значение; в противном случае — значение **false** .

## <a name="link_target_notification"></a>link_target_notification

Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим блоком сообщений `overwrite_buffer`.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на вновь связанный целевой объект.

## <a name="dtor"></a>~ overwrite_buffer

Уничтожает блок сообщений `overwrite_buffer`.

```cpp
~overwrite_buffer();
```

## <a name="ctor"></a>overwrite_buffer

Конструирует блок сообщений `overwrite_buffer`.

```cpp
overwrite_buffer();

overwrite_buffer(
    filter_method const& _Filter);

overwrite_buffer(
    Scheduler& _PScheduler);

overwrite_buffer(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Параметры

*_Filter*<br/>
Функция фильтра, которая определяет, следует ли принимать предлагаемые сообщения.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `overwrite_buffer` .

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `overwrite_buffer` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Remarks

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Тип `filter_method` — это функтор с сигнатурой `bool (T const &)` который вызывается этим блоком `overwrite_buffer` обмена сообщениями, чтобы определить, должно ли оно принимать предложенное сообщение.

## <a name="propagate_message"></a>propagate_message

Асинхронно передает сообщение из блока `ISource` в этот `overwrite_buffer` блок сообщений. Вызывается методом `propagate` при вызове из исходного блока.

```cpp
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

Помещает `message _PMessage` в этом `overwrite_buffer` блоке обмена сообщениями и предлагает его всем связанным целевым объектам.

```cpp
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`, владельцем которого является этот `overwrite_buffer`.

### <a name="remarks"></a>Remarks

Этот метод перезаписывает текущее сообщение в `overwrite_buffer` с вновь принятым сообщением `_PMessage`.

## <a name="send_message"></a>send_message

Синхронно передает сообщение из блока `ISource` в этот `overwrite_buffer` блок сообщений. Вызывается методом `send` при вызове из исходного блока.

```cpp
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

## <a name="supports_anonymous_source"></a>supports_anonymous_source

Переопределяет метод `supports_anonymous_source`, чтобы указать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , поскольку блок не откладывает предлагаемые сообщения.

## <a name="release_message"></a>release_message

Освобождает предыдущее резервирование сообщения.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` освобожденного объекта `message`.

## <a name="reserve_message"></a>reserve_message

Резервирует сообщение, которое было предложено этим блоком `overwrite_buffer` Messaging.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` резервируемого объекта `message`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если сообщение было успешно зарезервировано; в противном случае — **значение false** .

### <a name="remarks"></a>Remarks

После вызова `reserve`, если он возвращает **значение true**, необходимо вызвать метод `consume` или `release`, чтобы получить или освободить владение сообщением.

## <a name="resume_propagation"></a>resume_propagation

Возобновляет распространение после освобождения резервирования.

```cpp
virtual void resume_propagation();
```

## <a name="value"></a>значений

Возвращает ссылку на текущие полезные данные сообщения, хранящегося в блоке сообщений `overwrite_buffer`.

```cpp
T value();
```

### <a name="return-value"></a>Возвращаемое значение

Полезные данные текущего сохраненного сообщения.

### <a name="remarks"></a>Remarks

Значение, хранящееся в `overwrite_buffer`, может измениться сразу после возврата этим методом. Этот метод будет ожидать, пока не будет получено сообщение, если в `overwrite_buffer`в данный момент не хранится ни одно сообщение.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс unbounded_buffer](unbounded-buffer-class.md)<br/>
[Класс single_assignment](single-assignment-class.md)
