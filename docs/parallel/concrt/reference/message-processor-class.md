---
title: Класс message_processor
ms.date: 11/04/2016
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
ms.openlocfilehash: be6cb1c614a41919663a4cc063da66679556e498
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295244"
---
# <a name="messageprocessor-class"></a>Класс message_processor

Класс `message_processor` — это абстрактный базовый класс для обработки объектов `message`. Упорядочивание сообщений не гарантируется.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class message_processor;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных полезных данных внутри сообщений обрабатываемые этим `message_processor` объекта.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`type`|Псевдоним для `T`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[async_send](#async_send)|При переопределении в производном классе размещает сообщения в блок асинхронно.|
|[sync_send](#sync_send)|При переопределении в производном классе размещает сообщения в блок синхронно.|
|[wait](#wait)|При переопределении в производном классе, ожидает завершения всех асинхронных операций.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание:|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|При переопределении в производном классе, выполняет прямой обработку сообщений в блок. Вызывается один раз при каждом добавлении нового сообщения и очередь оказывается пустой.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`message_processor`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

##  <a name="async_send"></a> async_send

При переопределении в производном классе размещает сообщения в блок асинхронно.

```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Объект `message` объекта для асинхронной отправки.

### <a name="remarks"></a>Примечания

Процессор реализации должны переопределять этот метод.

##  <a name="process_incoming_message"></a> process_incoming_message

При переопределении в производном классе, выполняет прямой обработку сообщений в блок. Вызывается один раз при каждом добавлении нового сообщения и очередь оказывается пустой.

```
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>Примечания

Этот метод необходимо переопределить реализации блоков сообщений.

##  <a name="sync_send"></a> sync_send

При переопределении в производном классе размещает сообщения в блок синхронно.

```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Объект `message` объект для отправки в синхронном режиме.

### <a name="remarks"></a>Примечания

Процессор реализации должны переопределять этот метод.

##  <a name="wait"></a> Подождите

При переопределении в производном классе, ожидает завершения всех асинхронных операций.

```
virtual void wait() = 0;
```

### <a name="remarks"></a>Примечания

Процессор реализации должны переопределять этот метод.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс ordered_message_processor](ordered-message-processor-class.md)
