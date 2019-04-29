---
title: Класс ordered_message_processor
ms.date: 11/04/2016
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
ms.openlocfilehash: b88544f399031a5f770fa39aa1f3300306158511
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394433"
---
# <a name="orderedmessageprocessor-class"></a>Класс ordered_message_processor

Класс `ordered_message_processor` представляет собой `message_processor`, который позволяет блокам обмена сообщениями обрабатывать сообщения в том порядке, в котором они их получают.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ordered_message_processor : public message_processor<T>;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных сообщений, обработанных обработчиком.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|`type`|Псевдоним для `T`.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[ordered_message_processor](#ctor)|Создает объект `ordered_message_processor`.|
|[~ ordered_message_processor деструктор](#dtor)|Уничтожает `ordered_message_processor` объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[async_send](#async_send)|Асинхронно добавляет сообщения в очередь и запускает задачу обработки, в том случае, если это еще не сделано. (Переопределяет [message_processor::async_send](message-processor-class.md#async_send).)|
|[Инициализация](#initialize)|Инициализирует `ordered_message_processor` объекта с группой соответствующий обратный вызов функции, планировщик и расписание.|
|[initialize_batched_processing](#initialize_batched_processing)|Инициализация обработки пакетных сообщений|
|[sync_send](#sync_send)|Синхронно ставит в очередь сообщения и запускает задачу обработки, в том случае, если это еще не сделано. (Переопределяет [message_processor::sync_send](message-processor-class.md#sync_send).)|
|[wait](#wait)|Ожидание прокрутки определенного процессора, используемое в деструкторах блоков сообщений, чтобы убедиться в том, что все задачи асинхронной обработки достаточное время для завершения перед удалением блока. (Переопределяет [message_processor::wait](message-processor-class.md#wait).)|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Функция обработки, которая вызывается асинхронно. Он удаляет сообщения из очереди и начинает их обработку. (Переопределяет [message_processor::process_incoming_message](message-processor-class.md#process_incoming_message).)|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[message_processor](message-processor-class.md)

`ordered_message_processor`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

##  <a name="async_send"></a> async_send

Асинхронно добавляет сообщения в очередь и запускает задачу обработки, в том случае, если это еще не сделано.

```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Указатель на сообщение.

##  <a name="initialize"></a> Инициализация

Инициализирует `ordered_message_processor` объекта с группой соответствующий обратный вызов функции, планировщик и расписание.

```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```

### <a name="parameters"></a>Параметры

*_PScheduler*<br/>
Указатель на планировщик для планирования простых задач.

*_PScheduleGroup*<br/>
Указатель на группу расписаний, которая будет использоваться для планирования простых задач.

*_Handler*<br/>
Функтор обработчик вызова во время обратного вызова.

##  <a name="initialize_batched_processing"></a> initialize_batched_processing

Инициализация обработки пакетных сообщений

```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```

### <a name="parameters"></a>Параметры

*_Processor*<br/>
Функтор процессора, вызывается во время обратного вызова.

*_Propagator*<br/>
Функтор распространитель, вызывается во время обратного вызова.

##  <a name="ctor"></a> ordered_message_processor

Создает объект `ordered_message_processor`.

```
ordered_message_processor();
```

### <a name="remarks"></a>Примечания

Это `ordered_message_processor` не будем планировать асинхронный или синхронный обработчики до `initialize` функция вызывается.

##  <a name="dtor"></a> ~ ordered_message_processor

Уничтожает `ordered_message_processor` объекта.

```
virtual ~ordered_message_processor();
```

### <a name="remarks"></a>Примечания

Ожидает в течение всех незавершенных асинхронных операций перед удалением процессора.

##  <a name="process_incoming_message"></a> process_incoming_message

Функция обработки, которая вызывается асинхронно. Он удаляет сообщения из очереди и начинает их обработку.

```
virtual void process_incoming_message();
```

##  <a name="sync_send"></a> sync_send

Синхронно ставит в очередь сообщения и запускает задачу обработки, в том случае, если это еще не сделано.

```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Указатель на сообщение.

##  <a name="wait"></a> Подождите

Ожидание прокрутки определенного процессора, используемое в деструкторах блоков сообщений, чтобы убедиться в том, что все задачи асинхронной обработки достаточное время для завершения перед удалением блока.

```
virtual void wait();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
