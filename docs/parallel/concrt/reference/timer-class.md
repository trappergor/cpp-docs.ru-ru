---
title: Класс timer
ms.date: 11/04/2016
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
ms.openlocfilehash: c39afc565a7ec775600b9c9fb6f15a89acdef57b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142532"
---
# <a name="timer-class"></a>Класс timer

Блок обмена сообщениями `timer` — это блок `source_block` с одной целью, который может отправлять сообщение своей цели по истечении указанного периода времени или через заданные интервалы времени.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных выходных сообщений этого блока.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[активности](#ctor)|Перегружен. Конструирует блок сообщений `timer`, который будет запускать заданное сообщение после указанного интервала.|
|[Деструктор ~ Timer](#dtor)|Уничтожает блок сообщений `timer`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[работу](#pause)|Останавливает блок сообщений `timer`. Если это повторяющийся `timer` блок сообщений, его можно перезапустить при последующем вызове `start()`. Для неповторяющихся таймеров это действие аналогично вызову `stop`.|
|[start](#start)|Запускает блок обмена сообщениями `timer`. Указанное число миллисекунд после вызова, указанное значение будет распространено в качестве `message`.|
|[stop](#stop)|Останавливает блок сообщений `timer`.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[accept_message](#accept_message)|Принимает сообщение, которое было предложено этим блоком `timer` сообщений, передавая владение вызывающему объекту.|
|[consume_message](#consume_message)|Использует сообщение, которое было ранее предложено `timer` и зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим блоком сообщений `timer`.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Пытается предложить сообщение, созданное блоком `timer`, во все связанные целевые объекты.|
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Резервирует сообщение, которое было предложено этим блоком `timer` Messaging. (Переопределяет [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Возобновляет распространение после освобождения резервирования. (Переопределяет [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

[source_block](source-block-class.md)

`timer`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept_message"></a>accept_message

Принимает сообщение, которое было предложено этим блоком `timer` сообщений, передавая владение вызывающему объекту.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` предлагаемого `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `message`, владельцем которого стал вызывающий объект.

## <a name="consume_message"></a>consume_message

Использует сообщение, которое было ранее предложено `timer` и зарезервировано целевым объектом, передавая владение вызывающему объекту.

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

## <a name="link_target_notification"></a>link_target_notification

Обратный вызов, уведомляющий о том, что новый целевой объект связан с этим блоком сообщений `timer`.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на вновь связанный целевой объект.

## <a name="pause"></a>работу

Останавливает блок сообщений `timer`. Если это повторяющийся `timer` блок сообщений, его можно перезапустить при последующем вызове `start()`. Для неповторяющихся таймеров это действие аналогично вызову `stop`.

```cpp
void pause();
```

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

Пытается предложить сообщение, созданное блоком `timer`, во все связанные целевые объекты.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```

## <a name="release_message"></a>release_message

Освобождает предыдущее резервирование сообщения.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` освобожденного объекта `message`.

## <a name="reserve_message"></a>reserve_message

Резервирует сообщение, которое было предложено этим блоком `timer` Messaging.

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

## <a name="start"></a>запустить

Запускает блок обмена сообщениями `timer`. Указанное число миллисекунд после вызова, указанное значение будет распространено в качестве `message`.

```cpp
void start();
```

## <a name="stop"></a>позиции

Останавливает блок сообщений `timer`.

```cpp
void stop();
```

## <a name="ctor"></a>активности

Конструирует блок сообщений `timer`, который будет запускать заданное сообщение после указанного интервала.

```cpp
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```

### <a name="parameters"></a>Параметры

*_Ms*<br/>
Число миллисекунд, которое должно пройти после вызова метода Start для указанного сообщения, чтобы передать его в нисходящее распространение.

*value*<br/>
Значение, которое будет распространяться дальше по истечении времени ожидания.

*_PTarget*<br/>
Целевой объект, в который таймер будет распространять свое сообщение.

*_Repeating*<br/>
Значение true показывает, что таймер будет срабатывать каждые `_Ms` миллисекунд.

*_Scheduler*<br/>
Запланированный объект `Scheduler`, в рамках которого запланирована задача распространения для `timer` блока обмена сообщениями.

*_ScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `timer` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Remarks

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_Scheduler` или `_ScheduleGroup` .

## <a name="dtor"></a>~ Timer

Уничтожает блок сообщений `timer`.

```cpp
~timer();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
