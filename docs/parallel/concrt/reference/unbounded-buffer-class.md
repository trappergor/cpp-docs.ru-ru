---
title: Класс unbounded_buffer
ms.date: 11/04/2016
f1_keywords:
- unbounded_buffer
- AGENTS/concurrency::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::dequeue
- AGENTS/concurrency::unbounded_buffer::enqueue
- AGENTS/concurrency::unbounded_buffer::accept_message
- AGENTS/concurrency::unbounded_buffer::consume_message
- AGENTS/concurrency::unbounded_buffer::link_target_notification
- AGENTS/concurrency::unbounded_buffer::process_input_messages
- AGENTS/concurrency::unbounded_buffer::propagate_message
- AGENTS/concurrency::unbounded_buffer::propagate_output_messages
- AGENTS/concurrency::unbounded_buffer::release_message
- AGENTS/concurrency::unbounded_buffer::reserve_message
- AGENTS/concurrency::unbounded_buffer::resume_propagation
- AGENTS/concurrency::unbounded_buffer::send_message
- AGENTS/concurrency::unbounded_buffer::supports_anonymous_source
ms.assetid: 6b1a939a-1819-4385-b1d8-708f83d4ec47
ms.openlocfilehash: d0f2f81957ee88d4263c6acd879bd286c95631eb
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142336"
---
# <a name="unbounded_buffer-class"></a>Класс unbounded_buffer

Блок обмена сообщениями `unbounded_buffer` — это упорядоченный блок `propagator_block` с несколькими целями и несколькими источниками, который может хранить неограниченное число сообщений.

## <a name="syntax"></a>Синтаксис

```cpp
template<
   class             _Type
>
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;
```

### <a name="parameters"></a>Параметры

*_Type*<br/>
Тип полезных данных сообщений, хранимых и распространяемых буфером.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[unbounded_buffer](#ctor)|Перегружен. Конструирует блок сообщений `unbounded_buffer`.|
|[Деструктор ~ unbounded_buffer](#dtor)|Уничтожает блок сообщений `unbounded_buffer`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[вывода из очереди](#dequeue)|Удаляет элемент из блока сообщений `unbounded_buffer`.|
|[очередь](#enqueue)|Добавляет элемент в блок сообщений `unbounded_buffer`.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[accept_message](#accept_message)|Принимает сообщение, которое было предложено этим блоком `unbounded_buffer` сообщений, передавая владение вызывающему объекту.|
|[consume_message](#consume_message)|Использует сообщение, которое было ранее предложено блоком `unbounded_buffer` Messaging и зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим блоком сообщений `unbounded_buffer`.|
|[process_input_messages](#process_input_messages)|Помещает `message` `_PMessage` в этом `unbounded_buffer` блоке обмена сообщениями и пытается предложить его всем связанным целевым объектам.|
|[propagate_message](#propagate_message)|Асинхронно передает сообщение из блока `ISource` в этот `unbounded_buffer` блок сообщений. Вызывается методом `propagate` при вызове из исходного блока.|
|[propagate_output_messages](#propagate_output_messages)|Помещает `message` `_PMessage` в этом `unbounded_buffer` блоке обмена сообщениями и пытается предложить его всем связанным целевым объектам. (Переопределяет [source_block::p ropagate_output_messages](source-block-class.md#propagate_output_messages).)|
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Резервирует сообщение, которое было предложено этим блоком `unbounded_buffer` Messaging. (Переопределяет [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Возобновляет распространение после освобождения резервирования. (Переопределяет [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Синхронно передает сообщение из блока `ISource` в этот `unbounded_buffer` блок сообщений. Вызывается методом `send` при вызове из исходного блока.|
|[supports_anonymous_source](#supports_anonymous_source)|Переопределяет метод `supports_anonymous_source`, чтобы указать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником. (Переопределяет метод [ITarget:: supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`unbounded_buffer`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept_message"></a>accept_message

Принимает сообщение, которое было предложено этим блоком `unbounded_buffer` сообщений, передавая владение вызывающему объекту.

```cpp
virtual message<_Type> * accept_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` предлагаемого `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `message`, владельцем которого стал вызывающий объект.

## <a name="consume_message"></a>consume_message

Использует сообщение, которое было ранее предложено блоком `unbounded_buffer` Messaging и зарезервировано целевым объектом, передавая владение вызывающему объекту.

```cpp
virtual message<_Type> * consume_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` используемого объекта `message`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `message`, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Remarks

Аналогично `accept`, но всегда предшествует вызов `reserve`.

## <a name="dequeue"></a>вывода из очереди

Удаляет элемент из блока сообщений `unbounded_buffer`.

```cpp
_Type dequeue();
```

### <a name="return-value"></a>Возвращаемое значение

Полезные данные сообщения, удаленные из `unbounded_buffer`.

## <a name="enqueue"></a>очередь

Добавляет элемент в блок сообщений `unbounded_buffer`.

```cpp
bool enqueue(
   _Type const&                 _Item
);
```

### <a name="parameters"></a>Параметры

*_Item*<br/>
Добавляемый элемент.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если элемент был принят, и **false** в противном случае.

## <a name="link_target_notification"></a>link_target_notification

Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим блоком сообщений `unbounded_buffer`.

```cpp
virtual void link_target_notification(
   _Inout_ ITarget<_Type> *                 _PTarget
);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на вновь связанный целевой объект.

## <a name="propagate_message"></a>propagate_message

Асинхронно передает сообщение из блока `ISource` в этот `unbounded_buffer` блок сообщений. Вызывается методом `propagate` при вызове из исходного блока.

```cpp
virtual message_status propagate_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md#message_status) указывает, что цель решила делать с сообщением.

## <a name="propagate_output_messages"></a>propagate_output_messages

Помещает `message` `_PMessage` в этом `unbounded_buffer` блоке обмена сообщениями и пытается предложить его всем связанным целевым объектам.

```cpp
virtual void propagate_output_messages();
```

### <a name="remarks"></a>Remarks

Если другое сообщение уже используется в `unbounded_buffer`, распространение на связанные целевые объекты не будет происходить, пока не будут приняты или использованы все предыдущие сообщения. Первая связанная цель для успешного `accept` или `consume` сообщения становится владельцем, а другая цель не может получить сообщение.

## <a name="process_input_messages"></a>process_input_messages

Помещает `message` `_PMessage` в этом `unbounded_buffer` блоке обмена сообщениями и пытается предложить его всем связанным целевым объектам.

```cpp
virtual void process_input_messages(
   _Inout_ message<_Type> *                 _PMessage
);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на сообщение, которое должно быть обработано.

## <a name="release_message"></a>release_message

Освобождает предыдущее резервирование сообщения.

```cpp
virtual void release_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` освобожденного объекта `message`.

## <a name="reserve_message"></a>reserve_message

Резервирует сообщение, которое было предложено этим блоком `unbounded_buffer` Messaging.

```cpp
virtual bool reserve_message(
   runtime_object_identity                 _MsgId
);
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

## <a name="send_message"></a>send_message

Синхронно передает сообщение из блока `ISource` в этот `unbounded_buffer` блок сообщений. Вызывается методом `send` при вызове из исходного блока.

```cpp
virtual message_status send_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md#message_status) указывает, что цель решила делать с сообщением.

## <a name="supports_anonymous_source"></a>supports_anonymous_source

Переопределяет метод `supports_anonymous_source`, чтобы указать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , поскольку блок не откладывает предлагаемые сообщения.

## <a name="ctor"></a>unbounded_buffer

Конструирует блок сообщений `unbounded_buffer`.

```cpp
unbounded_buffer();

unbounded_buffer(
   filter_method const&                 _Filter
);

unbounded_buffer(
   Scheduler&                 _PScheduler
);

unbounded_buffer(
   Scheduler&                 _PScheduler,
   filter_method const&                 _Filter
);

unbounded_buffer(
   ScheduleGroup&                 _PScheduleGroup
);

unbounded_buffer(
   ScheduleGroup&                 _PScheduleGroup,
   filter_method const&                 _Filter
);
```

### <a name="parameters"></a>Параметры

*_Filter*<br/>
Функция фильтра, которая определяет, следует ли принимать предлагаемые сообщения.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `unbounded_buffer` .

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `unbounded_buffer` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Remarks

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Тип `filter_method` — это функтор с сигнатурой `bool (_Type const &)` который вызывается этим блоком `unbounded_buffer` обмена сообщениями, чтобы определить, должно ли оно принимать предложенное сообщение.

## <a name="dtor"></a>~ unbounded_buffer

Уничтожает блок сообщений `unbounded_buffer`.

```cpp
~unbounded_buffer();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс overwrite_buffer](overwrite-buffer-class.md)<br/>
[Класс single_assignment](single-assignment-class.md)
