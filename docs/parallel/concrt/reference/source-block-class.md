---
title: Класс source_block | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4a184e0fee76f3aa5bb8f7729250c03b10b9dfc
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163495"
---
# <a name="sourceblock-class"></a>Класс source_block

Класс `source_block` — это абстрактный базовый класс только для блоков источника. Класс предоставляет основные функции управления соединениями, а также проверки распространенных ошибок.

## <a name="syntax"></a>Синтаксис

```
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```

#### <a name="parameters"></a>Параметры

*_TargetLinkRegistry*<br/>
Реестр ссылок для использования для хранения целевых ссылок.

*_MessageProcessorType*<br/>
Тип процессора для обработки сообщений.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`target_iterator`|Итератор для прохода подключенных целевых объектов.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[source_block](#ctor)|Создает объект `source_block`.|
|[~ source_block деструктор](#dtor)|Уничтожает `source_block` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Принять](#accept)|Принимает сообщение, предложенное это `source_block` объекта, передавая владение вызывающему объекту.|
|[acquire_ref](#acquire_ref)|Получает значение счетчика ссылок на это `source_block` объекта, чтобы предотвратить удаление данных.|
|[Использование](#consume)|Получает сообщение, ранее предложенного этим объектом `source_block` объекта и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|
|[link_target](#link_target)|Это связывает целевой блок `source_block` объекта.|
|[release](#release)|Освобождает предыдущее резервирование сообщение об успешной.|
|[release_ref](#release_ref)|Освобождает значение счетчика ссылок на это `source_block` объекта.|
|[reserve](#reserve)|Резервирует сообщение, ранее предложенного этим объектом `source_block` объекта.|
|[unlink_target](#unlink_target)|Удаляет связь с целевым блоком и это `source_block` объекта.|
|[unlink_targets](#unlink_targets)|Удаляет связь всех целевых блоков из этого `source_block` объекта. (Переопределяет [ISource::unlink_targets](isource-class.md#unlink_targets).)|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[accept_message](#accept_message)|При переопределении в производном классе, принимает сообщение, предложенное источником. Блоки сообщений должны переопределять этот метод для проверки `_MsgId` и вернуть сообщение.|
|[async_send](#async_send)|Асинхронно добавляет сообщения в очередь и запускает задачу распространения, в том случае, если это еще не сделано|
|[consume_message](#consume_message)|При переопределении в производном классе, получает сообщение, которое было ранее зарезервировано.|
|[enable_batched_processing](#enable_batched_processing)|Активирует пакетную обработку для этого блока.|
|[initialize_source](#initialize_source)|Инициализирует `message_propagator` в рамках этого `source_block`.|
|[link_target_notification](#link_target_notification)|Обратный вызов, который уведомляет о том, что новый целевой объект была связана с это `source_block` объекта.|
|[process_input_messages](#process_input_messages)|Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.|
|[propagate_output_messages](#propagate_output_messages)|Распространение сообщений в целевые объекты.|
|[propagate_to_any_targets](#propagate_to_any_targets)|При переопределении в производном классе, передает заданное сообщение или на все связанные целевые объекты. Это является основной способ распространения для блоков сообщений.|
|[release_message](#release_message)|При переопределении в производном классе освобождает предыдущее резервирование сообщения.|
|[remove_targets](#remove_targets)|Удаляет все целевые ссылки для этого исходного блока. Должен быть вызван из деструктора.|
|[reserve_message](#reserve_message)|При переопределении в производном классе резервирует сообщение, ранее предложенного этим объектом `source_block` объекта.|
|[resume_propagation](#resume_propagation)|При переопределении в производном классе возобновляет распространение после выпуска резервирования.|
|[sync_send](#sync_send)|Синхронно ставит в очередь сообщения и запускает задачу распространения, в том случае, если это еще не сделано.|
|[unlink_target_notification](#unlink_target_notification)|Обратный вызов, который уведомляет о том, что целевой объект была удалена из этого `source_block` объекта.|
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|Ожидает завершения всех асинхронных операций распространения. Этот тип ожидания Ожидание прокрутки определенного используется в деструкторах блоков сообщений, чтобы убедиться в том, что для всех асинхронных операций распространения достаточное время для завершения перед удалением блока.|

## <a name="remarks"></a>Примечания

Блоки сообщений должен быть производным от этого блока, чтобы воспользоваться преимуществами управление ссылками и синхронизации, предоставляемые этим классом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

`source_block`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

##  <a name="accept"></a> Принять

Принимает сообщение, предложенное это `source_block` объекта, передавая владение вызывающему объекту.

```
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из предложенные `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, который вызывает `accept` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объекта, что вызывающий объект теперь принадлежит.

### <a name="remarks"></a>Примечания

Метод вызывает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключения Если параметр `_PTarget` является `NULL`.

`accept` Метод вызывается целевого объекта, пока сообщение предлагается это `ISource` блока. Для сообщения возвращаемого указателя может отличаться от тот, который передается в `propagate` метод `ITarget` заблокировать, если этот источник решает создать копию сообщения.

##  <a name="accept_message"></a> accept_message

При переопределении в производном классе, принимает сообщение, предложенное источником. Блоки сообщений должны переопределять этот метод для проверки `_MsgId` и вернуть сообщение.

```
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
Идентификатор объекта среды выполнения `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение, которое теперь принадлежит вызывающий объект.

### <a name="remarks"></a>Примечания

Для передачи владения исходный указатель сообщения должно быть возвращено. Для поддержания владения копию полезных данных сообщения должен быть выполнено и возвращено.

##  <a name="acquire_ref"></a> acquire_ref

Получает значение счетчика ссылок на это `source_block` объекта, чтобы предотвратить удаление данных.

```
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объект, который, связанным с данного источника во время `link_target` метод.

##  <a name="async_send"></a> async_send

Асинхронно добавляет сообщения в очередь и запускает задачу распространения, в том случае, если это еще не сделано

```
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Указатель на `message` объект для асинхронной передачи.

##  <a name="consume"></a> Использование

Получает сообщение, ранее предложенного этим объектом `source_block` объекта и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.

```
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Зарезервированных `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, который вызывает `consume` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объекта, что вызывающий объект теперь принадлежит.

### <a name="remarks"></a>Примечания

Метод вызывает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключения Если параметр `_PTarget` является `NULL`.

Метод вызывает [bad_target](bad-target-class.md) исключения Если параметр `_PTarget` не представляет целевой объект, который вызывается `reserve`.

`consume` Метод аналогичен методу `accept`, но всегда должно начинаться с помощью вызова `reserve` которые вернули **true**.

##  <a name="consume_message"></a> consume_message

При переопределении в производном классе, получает сообщение, которое было ранее зарезервировано.

```
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из `message` объекта использованное.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение, которое теперь принадлежит вызывающий объект.

### <a name="remarks"></a>Примечания

Аналогичную `accept`, но всегда предшествует вызов `reserve`.

##  <a name="enable_batched_processing"></a> enable_batched_processing

Активирует пакетную обработку для этого блока.

```
void enable_batched_processing();
```

##  <a name="initialize_source"></a> initialize_source

Инициализирует `message_propagator` в рамках этого `source_block`.

```
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Параметры

*_PScheduler*<br/>
Планировщик для планирования задач.

*_PScheduleGroup*<br/>
Группа расписаний, которая будет использоваться для планирования задач.

##  <a name="link_target"></a> link_target

Это связывает целевой блок `source_block` объекта.

```
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на `ITarget` блок, чтобы связать это `source_block` объекта.

### <a name="remarks"></a>Примечания

Метод вызывает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключения Если параметр `_PTarget` является `NULL`.

##  <a name="link_target_notification"></a> link_target_notification

Обратный вызов, который уведомляет о том, что новый целевой объект была связана с это `source_block` объекта.

```
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```

##  <a name="process_input_messages"></a> process_input_messages

Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.

```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на сообщение, которое должен обрабатываться.

##  <a name="propagate_output_messages"></a> propagate_output_messages

Распространение сообщений в целевые объекты.

```
virtual void propagate_output_messages();
```

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

При переопределении в производном классе, передает заданное сообщение или на все связанные целевые объекты. Это является основной способ распространения для блоков сообщений.

```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на сообщение, распространяемое.

##  <a name="release"></a> выпуск

Освобождает предыдущее резервирование сообщение об успешной.

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Зарезервированных `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, который вызывает `release` метод.

### <a name="remarks"></a>Примечания

Метод вызывает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключения Если параметр `_PTarget` является `NULL`.

Метод вызывает [bad_target](bad-target-class.md) исключения Если параметр `_PTarget` не представляет целевой объект, который вызывается `reserve`.

##  <a name="release_message"></a> release_message

При переопределении в производном классе освобождает предыдущее резервирование сообщения.

```
virtual void release_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из `message` объекта освобождение.

##  <a name="release_ref"></a> release_ref

Освобождает значение счетчика ссылок на это `source_block` объекта.

```
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, который вызывает этот метод.

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объект, который является, связь которого с данного источника. Блок источника может освободить все ресурсы, зарезервированные для целевой блок.

##  <a name="remove_targets"></a> remove_targets

Удаляет все целевые ссылки для этого исходного блока. Должен быть вызван из деструктора.

```
void remove_targets();
```

##  <a name="reserve"></a> Резерв

Резервирует сообщение, ранее предложенного этим объектом `source_block` объекта.

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из предложенные `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, который вызывает `reserve` метод.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если сообщение было успешно зарезервировано, **false** в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.

### <a name="remarks"></a>Примечания

Метод вызывает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключения Если параметр `_PTarget` является `NULL`.

После вызова метода `reserve`, если он завершается успешно, следует вызвать `consume` или `release` чтобы принять или высвободить владение сообщением, соответственно.

##  <a name="reserve_message"></a> reserve_message

При переопределении в производном классе резервирует сообщение, ранее предложенного этим объектом `source_block` объекта.

```
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из `message` объекта резервируются.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если сообщение было успешно зарезервировано, **false** в противном случае.

### <a name="remarks"></a>Примечания

После `reserve` вызывается, если он возвращает **true**, либо `consume` или `release` необходимо вызвать, чтобы принять или высвободить владение сообщением.

##  <a name="resume_propagation"></a> resume_propagation

При переопределении в производном классе возобновляет распространение после выпуска резервирования.

```
virtual void resume_propagation() = 0;
```

##  <a name="ctor"></a> source_block

Создает объект `source_block`.

```
source_block();
```

##  <a name="dtor"></a> ~ source_block

Уничтожает `source_block` объекта.

```
virtual ~source_block();
```

##  <a name="sync_send"></a> sync_send

Синхронно ставит в очередь сообщения и запускает задачу распространения, в том случае, если это еще не сделано.

```
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Указатель на `message` объект для синхронной отправки.

##  <a name="unlink_target"></a> unlink_target

Удаляет связь с целевым блоком и это `source_block` объекта.

```
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на `ITarget` блок, чтобы удалить связь из этого `source_block` объекта.

### <a name="remarks"></a>Примечания

Метод вызывает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключения Если параметр `_PTarget` является `NULL`.

##  <a name="unlink_target_notification"></a> unlink_target_notification

Обратный вызов, который уведомляет о том, что целевой объект была удалена из этого `source_block` объекта.

```
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
`ITarget` Блок, была удалена.

##  <a name="unlink_targets"></a> unlink_targets

Удаляет связь всех целевых блоков из этого `source_block` объекта.

```
virtual void unlink_targets();
```

##  <a name="wait_for_outstanding_async_sends"></a> wait_for_outstanding_async_sends

Ожидает завершения всех асинхронных операций распространения. Этот тип ожидания Ожидание прокрутки определенного используется в деструкторах блоков сообщений, чтобы убедиться в том, что для всех асинхронных операций распространения достаточное время для завершения перед удалением блока.

```
void wait_for_outstanding_async_sends();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс ISource](isource-class.md)
