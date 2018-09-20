---
title: Класс Timer | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b821dcc3426c6e1d9f3cd2f2ff8eb057197ca8d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416205"
---
# <a name="timer-class"></a>Класс timer

Блок обмена сообщениями `timer` — это блок `source_block` с одной целью, который может отправлять сообщение своей цели по истечении указанного периода времени или через заданные интервалы времени.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных выходных сообщений этого блока.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Таймера](#ctor)|Перегружен. Создает `timer` блок обмена сообщениями, которое будет срабатывать данное сообщение через указанное время.|
|[~ таймера деструктор](#dtor)|Уничтожает `timer` блок обмена сообщениями.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Приостановка](#pause)|Останавливает `timer` блок обмена сообщениями. Если это повторяющееся `timer` блоке сообщений, его можно перезапустить с последующем `start()` вызова. — Для неповторяющихся таймеров, это имеет тот же эффект, что `stop` вызова.|
|[start](#start)|Запускает `timer` блок обмена сообщениями. Указанное число миллисекунд, после этого вызывается, указанное значение будет распространяться подчиненных как `message`.|
|[Остановить](#stop)|Останавливает `timer` блок обмена сообщениями.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[accept_message](#accept_message)|Принимает сообщение, предложенное это `timer` блок обмена сообщениями, передача вызывающему объекту.|
|[consume_message](#consume_message)|Получает сообщение, было предложено `timer` и зарезервированного целевым объектом, передавая владение вызывающему объекту.|
|[link_target_notification](#link_target_notification)|Обратный вызов, который уведомляет о том, что новый целевой объект была связана с это `timer` блок обмена сообщениями.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Пытается предложить сообщение, созданное `timer` блок ко всем связанным целевым объектам.|
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block::release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Резервирует сообщение, ранее предложенного этим объектом `timer` блок обмена сообщениями. (Переопределяет [source_block::reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Возобновляет распространение после выпуска резервирования. (Переопределяет [source_block::resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

[source_block](source-block-class.md)

`timer`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

##  <a name="accept_message"></a> accept_message

Принимает сообщение, предложенное это `timer` блок обмена сообщениями, передача вызывающему объекту.

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из предложенные `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объекта, что вызывающий объект теперь принадлежит.

##  <a name="consume_message"></a> consume_message

Получает сообщение, было предложено `timer` и зарезервированного целевым объектом, передавая владение вызывающему объекту.

```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из `message` объекта использованное.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объекта, что вызывающий объект теперь принадлежит.

### <a name="remarks"></a>Примечания

Аналогичную `accept`, но всегда предшествует вызов `reserve`.

##  <a name="link_target_notification"></a> link_target_notification

Обратный вызов, который уведомляет о том, что новый целевой объект была связана с это `timer` блок обмена сообщениями.

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на только что привязанный целевой объект.

##  <a name="pause"></a> Приостановка

Останавливает `timer` блок обмена сообщениями. Если это повторяющееся `timer` блоке сообщений, его можно перезапустить с последующем `start()` вызова. — Для неповторяющихся таймеров, это имеет тот же эффект, что `stop` вызова.

```
void pause();
```

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

Пытается предложить сообщение, созданное `timer` блок ко всем связанным целевым объектам.

```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```

##  <a name="release_message"></a> release_message

Освобождает предыдущее резервирование сообщения.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из `message` объекта освобождение.

##  <a name="reserve_message"></a> reserve_message

Резервирует сообщение, ранее предложенного этим объектом `timer` блок обмена сообщениями.

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из `message` объекта резервируются.

### <a name="return-value"></a>Возвращаемое значение

`true` Если сообщение было успешно зарезервировано, `false` в противном случае.

### <a name="remarks"></a>Примечания

После `reserve` вызывается, если он возвращает `true`, либо `consume` или `release` необходимо вызвать, чтобы принять или высвободить владение сообщением.

##  <a name="resume_propagation"></a> resume_propagation

Возобновляет распространение после выпуска резервирования.

```
virtual void resume_propagation();
```

##  <a name="start"></a> Запуск

Запускает `timer` блок обмена сообщениями. Указанное число миллисекунд, после этого вызывается, указанное значение будет распространяться подчиненных как `message`.

```
void start();
```

##  <a name="stop"></a> Остановить

Останавливает `timer` блок обмена сообщениями.

```
void stop();
```

##  <a name="ctor"></a> Таймера

Создает `timer` блок обмена сообщениями, которое будет срабатывать данное сообщение через указанное время.

```
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
Количество миллисекунд, которое должно пройти после вызова для запуска для указанного сообщения распространяться на более низком уровне.

*значение*<br/>
Значение, которое будет распространяться более низком уровне, по истечении таймера.

*_PTarget*<br/>
Целевой объект, к которому таймер распространяет его сообщение.

*_Repeating*<br/>
Значение true указывает, что таймер будет срабатывать периодически каждый `_Ms` миллисекунд.

*_Scheduler*<br/>
`Scheduler` Объекта, в течение которого задача распространения для `timer` блок обмена сообщениями запланировано запланировано.

*_ScheduleGroup*<br/>
`ScheduleGroup` Объекта, в течение которого задача распространения для `timer` запланировано блок обмена сообщениями. Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Примечания

Среда выполнения использует планировщик по умолчанию, если вы не укажете `_Scheduler` или `_ScheduleGroup` параметров.

##  <a name="dtor"></a> ~ timer

Уничтожает `timer` блок обмена сообщениями.

```
~timer();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
