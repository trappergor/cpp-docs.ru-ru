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
ms.openlocfilehash: 4214c43fa0d0ab8fdd29ed54738c19f72a07267a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138957"
---
# <a name="multitype_join-class"></a>Класс multitype_join

Блок обмена сообщениями `multitype_join` — это блок с несколькими источниками и одной целью, который объединяет сообщения разных типов от каждого из своих источников и предлагает кортеж объединенных сообщений своему целевому объекту.

## <a name="syntax"></a>Синтаксис

```cpp
template<
    typename T,
    join_type _Jtype = non_greedy
>
class multitype_join: public ISource<typename _Unwrap<T>::type>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных `tuple` сообщений, соединяемых и распространяемых блоком.

*_Jtype*<br/>
Тип `join` блока: `greedy` или `non_greedy`

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Description|
|----------|-----------------|
|`type`|Псевдоним типа для `T`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[multitype_join](#ctor)|Перегружен. Создает блок обмена сообщениями `multitype_join` .|
|[Деструктор ~ multitype_join](#dtor)|Уничтожает блок сообщений `multitype_join`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[гласит](#accept)|Принимает сообщение, предложенное этим блоком `multitype_join`, передавая владение вызывающему объекту.|
|[acquire_ref](#acquire_ref)|Получает число ссылок на этот блок сообщений `multitype_join`, чтобы предотвратить удаление.|
|[consume](#consume)|Использует сообщение, которое было ранее предложено `multitype_join` блоком обмена сообщениями и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[link_target](#link_target)|Связывает целевой блок с этим блоком сообщений `multitype_join`.|
|[release](#release)|Освобождает предыдущее успешное резервирование сообщения.|
|[release_ref](#release_ref)|Освобождает счетчик ссылок на этом `multiple_join` блоке сообщений.|
|[reserve](#reserve)|Резервирует сообщение, которое было предложено этим блоком `multitype_join` Messaging.|
|[unlink_target](#unlink_target)|Отменяет связь с целевым блоком из этого блока сообщений `multitype_join`.|
|[unlink_targets](#unlink_targets)|Отменяет связь со всеми целевыми объектами из этого блока сообщений `multitype_join`. (Переопределяет метод [ISource:: unlink_targets](isource-class.md#unlink_targets).)|

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

`multitype_join`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept"></a>гласит

Принимает сообщение, предложенное этим блоком `multitype_join`, передавая владение вызывающему объекту.

```cpp
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `accept`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение о том, что вызывающий объект теперь является владельцем.

## <a name="acquire_ref"></a>acquire_ref

Получает число ссылок на этот блок сообщений `multitype_join`, чтобы предотвратить удаление.

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Remarks

Этот метод вызывается объектом `ITarget`, который связан с этим источником во время выполнения метода `link_target`.

## <a name="consume"></a>потребляющие

Использует сообщение, которое было ранее предложено `multitype_join` блоком обмена сообщениями и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.

```cpp
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` зарезервированного объекта `message`.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `consume`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `message`, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Remarks

Метод `consume` аналогичен `accept`, но перед ним всегда должен предшествовать вызов `reserve`, возвращающий **значение true**.

## <a name="link_target"></a>link_target

Связывает целевой блок с этим блоком сообщений `multitype_join`.

```cpp
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на блок `ITarget`, связываемый с этим блоком сообщений `multitype_join`.

## <a name="ctor"></a>multitype_join

Создает блок обмена сообщениями `multitype_join` .

```cpp
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

*_Join*<br/>
Блок обмена сообщениями `multitype_join` , из которого выполняется копирование. Обратите внимание, что исходный объект становится потерянным, превращая этот конструктор в конструктор перемещения.

### <a name="remarks"></a>Remarks

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Конструкция перемещения не выполняется при блокировке. Это означает, что пользователь должен убедиться в отсутствии простых задач во время перемещения. В противном случае могут возникнуть многочисленные гонки, приводящие к исключениям или недопустимому состоянию.

## <a name="dtor"></a>~ multitype_join

Уничтожает блок сообщений `multitype_join`.

```cpp
~multitype_join();
```

## <a name="release"></a>отпускании

Освобождает предыдущее успешное резервирование сообщения.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` освобожденного объекта `message`.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `release`.

## <a name="release_ref"></a>release_ref

Освобождает счетчик ссылок на этом `multiple_join` блоке сообщений.

```cpp
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Remarks

Этот метод вызывается объектом `ITarget`, связь с которым удаляется из этого источника. Блоку источника разрешено освобождать все ресурсы, зарезервированные для целевого блока.

## <a name="reserve"></a>предназначен

Резервирует сообщение, которое было предложено этим блоком `multitype_join` Messaging.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` резервируемого объекта `message`.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `reserve`.

### <a name="return-value"></a>Возвращаемое значение

`true`, если сообщение было успешно зарезервировано, `false` в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.

### <a name="remarks"></a>Remarks

После вызова `reserve`, если он выполняется, необходимо вызвать метод `consume` или `release`, чтобы получить или предоставить право на владение сообщениями соответственно.

## <a name="unlink_target"></a>unlink_target

Отменяет связь с целевым блоком из этого блока сообщений `multitype_join`.

```cpp
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на блок `ITarget`, который нужно удалить из этого `multitype_join` блока обмена сообщениями.

## <a name="unlink_targets"></a>unlink_targets

Отменяет связь со всеми целевыми объектами из этого блока сообщений `multitype_join`.

```cpp
virtual void unlink_targets();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс choice](choice-class.md)<br/>
[Класс join](join-class.md)
