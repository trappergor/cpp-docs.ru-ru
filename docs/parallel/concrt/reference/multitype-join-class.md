---
title: Класс multitype_join
ms.date: 11/04/2016
f1_keywords:
- multitype_join
- AGENTS/concurrency::multitype_join
- AGENTS/concurrency::multitype_join::multitype_join
- AGENTS/concurrency::multitype_join::accept
- AGENTS/concurrency::multitype_join::acquire_ref
- AGENTS/concurrency::multitype_join::consume
- AGENTS/concurrency::multitype_join::link_target
- AGENTS/concurrency::multitype_join::release
- AGENTS/concurrency::multitype_join::release_ref
- AGENTS/concurrency::multitype_join::reserve
- AGENTS/concurrency::multitype_join::unlink_target
- AGENTS/concurrency::multitype_join::unlink_targets
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
ms.openlocfilehash: 2fd94ef072fcab9af076fcdfa1b5c094d77f89c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547411"
---
# <a name="multitypejoin-class"></a>Класс multitype_join

Блок обмена сообщениями `multitype_join` — это блок с несколькими источниками и одной целью, который объединяет сообщения разных типов от каждого из своих источников и предлагает кортеж объединенных сообщений своему целевому объекту.

## <a name="syntax"></a>Синтаксис

```
template<
    typename T,
    join_type _Jtype = non_greedy
>
class multitype_join: public ISource<typename _Unwrap<T>::type>;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
`tuple` Тип полезных данных сообщений, объединенных и распространенных блоком.

*_Jtype*<br/>
Тип объекта `join` блок, это, либо `greedy` или `non_greedy`

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`type`|Псевдоним для `T`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[multitype_join](#ctor)|Перегружен. Создает блок обмена сообщениями `multitype_join` .|
|[~ multitype_join деструктор](#dtor)|Уничтожает `multitype_join` блок обмена сообщениями.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Принять](#accept)|Принимает сообщение, предложенное это `multitype_join` блоком, передавая владение вызывающему объекту.|
|[acquire_ref](#acquire_ref)|Получает значение счетчика ссылок на это `multitype_join` блок обмена сообщениями, чтобы предотвратить удаление данных.|
|[Использование](#consume)|Получает сообщение, было предложено `multitype_join` блоке сообщений и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|
|[link_target](#link_target)|Это связывает целевой блок `multitype_join` блок обмена сообщениями.|
|[release](#release)|Освобождает предыдущее резервирование сообщение об успешной.|
|[release_ref](#release_ref)|Освобождает значение счетчика ссылок на это `multiple_join` блок обмена сообщениями.|
|[reserve](#reserve)|Резервирует сообщение, ранее предложенного этим объектом `multitype_join` блок обмена сообщениями.|
|[unlink_target](#unlink_target)|Удаляет связь с целевым блоком и это `multitype_join` блок обмена сообщениями.|
|[unlink_targets](#unlink_targets)|Удаляет связь всех целевых объектов из данного `multitype_join` блок обмена сообщениями. (Переопределяет [ISource::unlink_targets](isource-class.md#unlink_targets).)|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

`multitype_join`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

##  <a name="accept"></a> Принять

Принимает сообщение, предложенное это `multitype_join` блоком, передавая владение вызывающему объекту.

```
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из предложенные `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, который вызывает `accept` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение, которое теперь принадлежит вызывающий объект.

##  <a name="acquire_ref"></a> acquire_ref

Получает значение счетчика ссылок на это `multitype_join` блок обмена сообщениями, чтобы предотвратить удаление данных.

```
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, который вызывает этот метод.

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объект, который, связанным с данного источника во время `link_target` метод.

##  <a name="consume"></a> Использование

Получает сообщение, было предложено `multitype_join` блоке сообщений и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.

```
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Зарезервированных `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, который вызывает `consume` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объекта, что вызывающий объект теперь принадлежит.

### <a name="remarks"></a>Примечания

`consume` Метод аналогичен методу `accept`, но всегда должно начинаться с помощью вызова `reserve` которые вернули **true**.

##  <a name="link_target"></a> link_target

Это связывает целевой блок `multitype_join` блок обмена сообщениями.

```
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на `ITarget` блок, чтобы связать это `multitype_join` блок обмена сообщениями.

##  <a name="ctor"></a> multitype_join

Создает блок обмена сообщениями `multitype_join` .

```
explicit multitype_join(
    T _Tuple);

multitype_join(
    Scheduler& _PScheduler,
    T _Tuple);

multitype_join(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

multitype_join(
    multitype_join&& _Join);
```

### <a name="parameters"></a>Параметры

*_Tuple*<br/>
Объект `tuple` источников для этого блока обмена сообщениями `multitype_join` .

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` .

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` . Используемый объект `Scheduler` подразумевается группой расписаний.

*_Объединить*<br/>
Блок обмена сообщениями `multitype_join` , из которого выполняется копирование. Обратите внимание, что исходный объект становится потерянным, превращая этот конструктор в конструктор перемещения.

### <a name="remarks"></a>Примечания

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Конструкция перемещения не выполняется при блокировке. Это означает, что пользователь должен убедиться в отсутствии простых задач во время перемещения. В противном случае могут возникнуть многочисленные гонки, приводящие к исключениям или недопустимому состоянию.

##  <a name="dtor"></a> ~ multitype_join

Уничтожает `multitype_join` блок обмена сообщениями.

```
~multitype_join();
```

##  <a name="release"></a> выпуск

Освобождает предыдущее резервирование сообщение об успешной.

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из `message` объекта освобождение.

*_PTarget*<br/>
Указатель на целевой блок, который вызывает `release` метод.

##  <a name="release_ref"></a> release_ref

Освобождает значение счетчика ссылок на это `multiple_join` блок обмена сообщениями.

```
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, который вызывает этот метод.

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объект, который является, связь которого с данного источника. Блок источника может освободить все ресурсы, зарезервированные для целевой блок.

##  <a name="reserve"></a> Резерв

Резервирует сообщение, ранее предложенного этим объектом `multitype_join` блок обмена сообщениями.

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` Из `message` объекта резервируются.

*_PTarget*<br/>
Указатель на целевой блок, который вызывает `reserve` метод.

### <a name="return-value"></a>Возвращаемое значение

`true` Если сообщение было успешно зарезервировано, `false` в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.

### <a name="remarks"></a>Примечания

После вызова метода `reserve`, если он завершается успешно, следует вызвать `consume` или `release` чтобы принять или высвободить владение сообщением, соответственно.

##  <a name="unlink_target"></a> unlink_target

Удаляет связь с целевым блоком и это `multitype_join` блок обмена сообщениями.

```
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на `ITarget` блок, чтобы удалить связь из этого `multitype_join` блок обмена сообщениями.

##  <a name="unlink_targets"></a> unlink_targets

Удаляет связь всех целевых объектов из данного `multitype_join` блок обмена сообщениями.

```
virtual void unlink_targets();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс choice](choice-class.md)<br/>
[Класс join](join-class.md)
