---
title: Класс join
ms.date: 11/04/2016
f1_keywords:
- join
- AGENTS/concurrency::join
- AGENTS/concurrency::join::join
- AGENTS/concurrency::join::accept_message
- AGENTS/concurrency::join::consume_message
- AGENTS/concurrency::join::link_target_notification
- AGENTS/concurrency::join::propagate_message
- AGENTS/concurrency::join::propagate_to_any_targets
- AGENTS/concurrency::join::release_message
- AGENTS/concurrency::join::reserve_message
- AGENTS/concurrency::join::resume_propagation
helpviewer_keywords:
- join class
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
ms.openlocfilehash: 23fc005a0c679576507c3a39ae37ce6c4545036b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668261"
---
# <a name="join-class"></a>Класс join

Блок обмена сообщениями `join` — это упорядоченный блок `propagator_block` с несколькими источниками и одной целью, который объединяет сообщения типа `T` от каждого из своих источников.

## <a name="syntax"></a>Синтаксис

```
template<class T,
    join_type _Jtype = non_greedy>
class join : public propagator_block<single_link_registry<ITarget<std::vector<T>>>,
    multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных сообщения объединенных и распространенных блоком.

*_Jtype*<br/>
Тип объекта `join` блок, это, либо `greedy` или `non_greedy`

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[join](#ctor)|Перегружен. Создает блок обмена сообщениями `join` .|
|[~ join деструктор](#dtor)|Уничтожает `join` блока.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[accept_message](#accept_message)|Принимает сообщение, предложенное это `join` блок обмена сообщениями, передача вызывающему объекту.|
|[consume_message](#consume_message)|Получает сообщение, было предложено `join` блоке сообщений и зарезервированных целевым объектом, передавая владение вызывающему объекту.|
|[link_target_notification](#link_target_notification)|Обратный вызов, который уведомляет о том, что новый целевой объект была связана с это `join` блок обмена сообщениями.|
|[propagate_message](#propagate_message)|Асинхронно передает сообщение от `ISource` блока к этому `join` блок обмена сообщениями. Он вызывается по `propagate` метод, при вызове исходного блока.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Создает выходное сообщение, содержащее сообщение для ввода из каждого источника, когда все они будут распространены на сообщение. Отправляет это сообщение выходные данные для каждого из его целевых объектов.|
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block::release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Резервирует сообщение, ранее предложенного этим объектом `join` блок обмена сообщениями. (Переопределяет [source_block::reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Возобновляет распространение после выпуска резервирования. (Переопределяет [source_block::resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`join`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

##  <a name="accept_message"></a> accept_message

Принимает сообщение, предложенное это `join` блок обмена сообщениями, передача вызывающему объекту.

```
virtual message<_OutputType>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из предложенные `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объекта, что вызывающий объект теперь принадлежит.

##  <a name="consume_message"></a> consume_message

Получает сообщение, было предложено `join` блоке сообщений и зарезервированных целевым объектом, передавая владение вызывающему объекту.

```
virtual message<_OutputType>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из `message` объекта использованное.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объекта, что вызывающий объект теперь принадлежит.

### <a name="remarks"></a>Примечания

Аналогичную `accept`, но всегда предшествует вызов `reserve`.

##  <a name="ctor"></a> соединения

Создает блок обмена сообщениями `join` .

```
join(
    size_t _NumInputs);

join(
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Параметры

*_NumInputs*<br/>
Количество входных данных, это `join` блок будет разрешен.

*_Фильтр*<br/>
Функция фильтра, который определяет, следует ли принять предлагаемые сообщения.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `join` .

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `join` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Примечания

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Тип `filter_method` является функтор с сигнатурой `bool (T const &)` которого вызывается этим `join` блок обмена сообщениями, чтобы определить ли он должен принять предложенное сообщение.

##  <a name="dtor"></a> ~ join

Уничтожает `join` блока.

```
~join();
```

##  <a name="link_target_notification"></a> link_target_notification

Обратный вызов, который уведомляет о том, что новый целевой объект была связана с это `join` блок обмена сообщениями.

```
virtual void link_target_notification(_Inout_ ITarget<std::vector<T>> *);
```

##  <a name="propagate_message"></a> propagate_message

Асинхронно передает сообщение от `ISource` блока к этому `join` блок обмена сообщениями. Он вызывается по `propagate` метод, при вызове исходного блока.

```
message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на блок источника, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

Объект [message_status](concurrency-namespace-enums.md) указывает, что целевой объект решил сделать с сообщением.

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

Создает выходное сообщение, содержащее сообщение для ввода из каждого источника, когда все они будут распространены на сообщение. Отправляет это сообщение выходные данные для каждого из его целевых объектов.

```
void propagate_to_any_targets(_Inout_opt_ message<_OutputType> *);
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

Резервирует сообщение, ранее предложенного этим объектом `join` блок обмена сообщениями.

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из предложенные `message` объекта.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если сообщение было успешно зарезервировано, **false** в противном случае.

### <a name="remarks"></a>Примечания

После `reserve` вызывается, если он возвращает **true**, либо `consume` или `release` необходимо вызвать, чтобы принять или высвободить владение сообщением.

##  <a name="resume_propagation"></a> resume_propagation

Возобновляет распространение после выпуска резервирования.

```
virtual void resume_propagation();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс choice](choice-class.md)<br/>
[Класс multitype_join](multitype-join-class.md)
