---
title: Класс source_block
ms.date: 11/04/2016
f1_keywords:
- source_block
- AGENTS/concurrency::source_block
- AGENTS/concurrency::source_block::source_block
- AGENTS/concurrency::source_block::accept
- AGENTS/concurrency::source_block::acquire_ref
- AGENTS/concurrency::source_block::consume
- AGENTS/concurrency::source_block::link_target
- AGENTS/concurrency::source_block::release
- AGENTS/concurrency::source_block::release_ref
- AGENTS/concurrency::source_block::reserve
- AGENTS/concurrency::source_block::unlink_target
- AGENTS/concurrency::source_block::unlink_targets
- AGENTS/concurrency::source_block::accept_message
- AGENTS/concurrency::source_block::async_send
- AGENTS/concurrency::source_block::consume_message
- AGENTS/concurrency::source_block::enable_batched_processing
- AGENTS/concurrency::source_block::initialize_source
- AGENTS/concurrency::source_block::link_target_notification
- AGENTS/concurrency::source_block::process_input_messages
- AGENTS/concurrency::source_block::propagate_output_messages
- AGENTS/concurrency::source_block::propagate_to_any_targets
- AGENTS/concurrency::source_block::release_message
- AGENTS/concurrency::source_block::remove_targets
- AGENTS/concurrency::source_block::reserve_message
- AGENTS/concurrency::source_block::resume_propagation
- AGENTS/concurrency::source_block::sync_send
- AGENTS/concurrency::source_block::unlink_target_notification
- AGENTS/concurrency::source_block::wait_for_outstanding_async_sends
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
ms.openlocfilehash: 3a0d69bc2e2904b1dcf37a7e9891d95bd869a610
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866138"
---
# <a name="source_block-class"></a>Класс source_block

Класс `source_block` — это абстрактный базовый класс только для блоков источника. Класс предоставляет основные функции управления соединениями, а также проверки распространенных ошибок.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```

### <a name="parameters"></a>Параметры

*_TargetLinkRegistry*<br/>
Свяжите реестр, который будет использоваться для хранения целевых ссылок.

*_MessageProcessorType*<br/>
Тип процессора для обработки сообщений.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Открытые определения типов

|Имя|Description|
|----------|-----------------|
|`target_iterator`|Итератор для прохода по подключенным целевым объектам.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[source_block](#ctor)|Формирует объект `source_block`.|
|[Деструктор ~ source_block](#dtor)|Уничтожает объект `source_block`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[гласит](#accept)|Принимает сообщение, предложенное этим `source_block` объектом, передавая владение вызывающему объекту.|
|[acquire_ref](#acquire_ref)|Получает счетчик ссылок на этот объект `source_block`, чтобы предотвратить удаление.|
|[consume](#consume)|Использует сообщение, которое было ранее предложено этим `source_block` объектом и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[link_target](#link_target)|Связывает целевой блок с этим `source_block` объектом.|
|[release](#release)|Освобождает предыдущее успешное резервирование сообщения.|
|[release_ref](#release_ref)|Освобождает счетчик ссылок на этот объект `source_block`.|
|[reserve](#reserve)|Резервирует сообщение, которое было ранее предложено этим объектом `source_block`.|
|[unlink_target](#unlink_target)|Отменяет связь с целевым блоком из этого `source_block` объекта.|
|[unlink_targets](#unlink_targets)|Отменяет связь всех целевых блоков с этим `source_block` объектом. (Переопределяет метод [ISource:: unlink_targets](isource-class.md#unlink_targets).)|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[accept_message](#accept_message)|При переопределении в производном классе принимает предлагаемое сообщение источником. Блоки сообщений должны переопределять этот метод для проверки `_MsgId` и возврата сообщения.|
|[async_send](#async_send)|Асинхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано.|
|[consume_message](#consume_message)|При переопределении в производном классе использует ранее зарезервированное сообщение.|
|[enable_batched_processing](#enable_batched_processing)|Активирует пакетную обработку для этого блока.|
|[initialize_source](#initialize_source)|Инициализирует `message_propagator` в этом `source_block`.|
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющий о том, что новый целевой объект связан с данным объектом `source_block`.|
|[process_input_messages](#process_input_messages)|Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.|
|[propagate_output_messages](#propagate_output_messages)|Распространение сообщений в целевые объекты.|
|[propagate_to_any_targets](#propagate_to_any_targets)|При переопределении в производном классе распространяет данное сообщение на все или все связанные целевые объекты. Это основная подпрограммы распространения для блоков сообщений.|
|[release_message](#release_message)|При переопределении в производном классе освобождает предыдущее резервирование сообщения.|
|[remove_targets](#remove_targets)|Удаляет все целевые ссылки для этого исходного блока. Его следует вызывать из деструктора.|
|[reserve_message](#reserve_message)|При переопределении в производном классе резервирует сообщение, которое ранее было предложено этим объектом `source_block`.|
|[resume_propagation](#resume_propagation)|При переопределении в производном классе возобновляет распространение после освобождения резервирования.|
|[sync_send](#sync_send)|Синхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано.|
|[unlink_target_notification](#unlink_target_notification)|Обратный вызов, уведомляющий об отсутствии связи цели с данным объектом `source_block`.|
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|Ожидает завершения всех асинхронных распространителей. Это время ожидания для этого распространителя используется в деструкторах блоков сообщений, чтобы убедиться в том, что все асинхронные распространители имеют достаточно времени для завершения перед уничтожением блока.|

## <a name="remarks"></a>Remarks

Блоки сообщений должны быть производными от этого блока, чтобы воспользоваться преимуществами управления ссылками и синхронизации, предоставляемыми этим классом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

`source_block`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept"></a>гласит

Принимает сообщение, предложенное этим `source_block` объектом, передавая владение вызывающему объекту.

```cpp
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `accept`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `message`, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если `_PTarget` параметра имеет значение `NULL`.

Метод `accept` вызывается целевым объектом, в то время как сообщение предлагается этим блоком `ISource`. Возвращаемый указатель на сообщение может отличаться от переданного в метод `propagate` блока `ITarget`, если этот источник решит создать копию сообщения.

## <a name="accept_message"></a>accept_message

При переопределении в производном классе принимает предлагаемое сообщение источником. Блоки сообщений должны переопределять этот метод для проверки `_MsgId` и возврата сообщения.

```cpp
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
Удостоверение объекта среды выполнения объекта `message`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение о том, что вызывающий объект теперь является владельцем.

### <a name="remarks"></a>Remarks

Чтобы передавать владение, должен быть возвращен указатель на исходный текст. Чтобы обеспечить владение, необходимо выполнить и вернуть копию полезных данных сообщения.

## <a name="acquire_ref"></a>acquire_ref

Получает счетчик ссылок на этот объект `source_block`, чтобы предотвратить удаление.

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```

### <a name="remarks"></a>Remarks

Этот метод вызывается объектом `ITarget`, который связан с этим источником во время выполнения метода `link_target`.

## <a name="async_send"></a>async_send

Асинхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано.

```cpp
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Указатель на объект `message` для асинхронной отправки.

## <a name="consume"></a>потребляющие

Использует сообщение, которое было ранее предложено этим `source_block` объектом и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.

```cpp
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` зарезервированного объекта `message`.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `consume`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `message`, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если `_PTarget` параметра имеет значение `NULL`.

Метод вызывает исключение [bad_target](bad-target-class.md) , если параметр `_PTarget` не представляет целевой объект, вызвавший `reserve`.

Метод `consume` аналогичен `accept`, но перед ним всегда должен предшествовать вызов `reserve`, возвращающий **значение true**.

## <a name="consume_message"></a>consume_message

При переопределении в производном классе использует ранее зарезервированное сообщение.

```cpp
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` используемого объекта `message`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение о том, что вызывающий объект теперь является владельцем.

### <a name="remarks"></a>Remarks

Аналогично `accept`, но всегда предшествует вызов `reserve`.

## <a name="enable_batched_processing"></a>enable_batched_processing

Активирует пакетную обработку для этого блока.

```cpp
void enable_batched_processing();
```

## <a name="initialize_source"></a>initialize_source

Инициализирует `message_propagator` в этом `source_block`.

```cpp
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Параметры

*_PScheduler*<br/>
Планировщик, который будет использоваться для планирования задач.

*_PScheduleGroup*<br/>
Группа расписаний, которая будет использоваться для планирования задач.

## <a name="link_target"></a>link_target

Связывает целевой блок с этим `source_block` объектом.

```cpp
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на блок `ITarget`, связываемый с этим `source_block` объектом.

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если `_PTarget` параметра имеет значение `NULL`.

## <a name="link_target_notification"></a>link_target_notification

Обратный вызов, уведомляющий о том, что новый целевой объект связан с данным объектом `source_block`.

```cpp
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```

## <a name="process_input_messages"></a>process_input_messages

Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на сообщение, которое должно быть обработано.

## <a name="propagate_output_messages"></a>propagate_output_messages

Распространение сообщений в целевые объекты.

```cpp
virtual void propagate_output_messages();
```

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

При переопределении в производном классе распространяет данное сообщение на все или все связанные целевые объекты. Это основная подпрограммы распространения для блоков сообщений.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на сообщение, которое должно быть распространено.

## <a name="release"></a>отпускании

Освобождает предыдущее успешное резервирование сообщения.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` зарезервированного объекта `message`.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `release`.

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если `_PTarget` параметра имеет значение `NULL`.

Метод вызывает исключение [bad_target](bad-target-class.md) , если параметр `_PTarget` не представляет целевой объект, вызвавший `reserve`.

## <a name="release_message"></a>release_message

При переопределении в производном классе освобождает предыдущее резервирование сообщения.

```cpp
virtual void release_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` освобожденного объекта `message`.

## <a name="release_ref"></a>release_ref

Освобождает счетчик ссылок на этот объект `source_block`.

```cpp
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Remarks

Этот метод вызывается объектом `ITarget`, связь с которым удаляется из этого источника. Блоку источника разрешено освобождать все ресурсы, зарезервированные для целевого блока.

## <a name="remove_targets"></a>remove_targets

Удаляет все целевые ссылки для этого исходного блока. Его следует вызывать из деструктора.

```cpp
void remove_targets();
```

## <a name="reserve"></a>предназначен

Резервирует сообщение, которое было ранее предложено этим объектом `source_block`.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `reserve`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если сообщение было успешно зарезервировано; в противном случае — **значение false** . Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если `_PTarget` параметра имеет значение `NULL`.

После вызова `reserve`, если он выполняется, необходимо вызвать метод `consume` или `release`, чтобы получить или предоставить право на владение сообщениями соответственно.

## <a name="reserve_message"></a>reserve_message

При переопределении в производном классе резервирует сообщение, которое ранее было предложено этим объектом `source_block`.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` резервируемого объекта `message`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если сообщение было успешно зарезервировано; в противном случае — **значение false** .

### <a name="remarks"></a>Remarks

После вызова `reserve`, если он возвращает **значение true**, необходимо вызвать метод `consume` или `release`, чтобы получить или освободить владение сообщением.

## <a name="resume_propagation"></a>resume_propagation

При переопределении в производном классе возобновляет распространение после освобождения резервирования.

```cpp
virtual void resume_propagation() = 0;
```

## <a name="ctor"></a>source_block

Формирует объект `source_block`.

```cpp
source_block();
```

## <a name="dtor"></a>~ source_block

Уничтожает объект `source_block`.

```cpp
virtual ~source_block();
```

## <a name="sync_send"></a>sync_send

Синхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано.

```cpp
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Указатель на объект `message` для синхронной отправки.

## <a name="unlink_target"></a>unlink_target

Отменяет связь с целевым блоком из этого `source_block` объекта.

```cpp
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на блок `ITarget`, который нужно удалить из этого `source_block` объекта.

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если `_PTarget` параметра имеет значение `NULL`.

## <a name="unlink_target_notification"></a>unlink_target_notification

Обратный вызов, уведомляющий об отсутствии связи цели с данным объектом `source_block`.

```cpp
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Несвязанный блок `ITarget`.

## <a name="unlink_targets"></a>unlink_targets

Отменяет связь всех целевых блоков с этим `source_block` объектом.

```cpp
virtual void unlink_targets();
```

## <a name="wait_for_outstanding_async_sends"></a>wait_for_outstanding_async_sends

Ожидает завершения всех асинхронных распространителей. Это время ожидания для этого распространителя используется в деструкторах блоков сообщений, чтобы убедиться в том, что все асинхронные распространители имеют достаточно времени для завершения перед уничтожением блока.

```cpp
void wait_for_outstanding_async_sends();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс ISource](isource-class.md)
