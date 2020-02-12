---
title: Класс choice
ms.date: 11/04/2016
f1_keywords:
- choice
- AGENTS/concurrency::choice
- AGENTS/concurrency::choice::choice
- AGENTS/concurrency::choice::accept
- AGENTS/concurrency::choice::acquire_ref
- AGENTS/concurrency::choice::consume
- AGENTS/concurrency::choice::has_value
- AGENTS/concurrency::choice::index
- AGENTS/concurrency::choice::link_target
- AGENTS/concurrency::choice::release
- AGENTS/concurrency::choice::release_ref
- AGENTS/concurrency::choice::reserve
- AGENTS/concurrency::choice::unlink_target
- AGENTS/concurrency::choice::unlink_targets
- AGENTS/concurrency::choice::value
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
ms.openlocfilehash: 3e718d0d34580d3bf2f13937159e431134631218
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142218"
---
# <a name="choice-class"></a>Класс choice

Блок обмена сообщениями `choice` — это блок с несколькими источниками и одной целью, который представляет взаимодействие потока управления с набором источников. Блок choice будет ожидать доступа к любому из нескольких источников для создания сообщения и распространит индекс источника, создавшего сообщение.

## <a name="syntax"></a>Синтаксис

```cpp
template<
    class T
>
class choice: public ISource<size_t>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип на основе `tuple`, представляющий полезные данные источников входных данных.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Description|
|----------|-----------------|
|`type`|Псевдоним типа для `T`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[усмотрени](#ctor)|Перегружен. Создает блок обмена сообщениями `choice` .|
|[Деструктор выбора ~](#dtor)|Уничтожает блок сообщений `choice`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[гласит](#accept)|Принимает сообщение, предложенное этим блоком `choice`, передавая владение вызывающему объекту.|
|[acquire_ref](#acquire_ref)|Получает число ссылок на этот блок сообщений `choice`, чтобы предотвратить удаление.|
|[consume](#consume)|Использует сообщение, которое было ранее предложено этим блоком `choice` сообщений и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[has_value](#has_value)|Проверяет, инициализирован ли этот блок обмена сообщениями `choice` с тем же значением.|
|[index](#index)|Возвращает индекс в `tuple` представляющий элемент, выбранный `choice` блоком обмена сообщениями.|
|[link_target](#link_target)|Связывает целевой блок с этим блоком сообщений `choice`.|
|[release](#release)|Освобождает предыдущее успешное резервирование сообщения.|
|[release_ref](#release_ref)|Освобождает счетчик ссылок на этом `choice` блоке сообщений.|
|[reserve](#reserve)|Резервирует сообщение, которое было предложено этим блоком `choice` Messaging.|
|[unlink_target](#unlink_target)|Отменяет связь с целевым блоком из этого блока сообщений `choice`.|
|[unlink_targets](#unlink_targets)|Отменяет связь со всеми целевыми объектами из этого блока сообщений `choice`. (Переопределяет метод [ISource:: unlink_targets](isource-class.md#unlink_targets).)|
|[value](#value)|Возвращает сообщение, чей индекс был выбран блоком сообщений `choice`.|

## <a name="remarks"></a>Remarks

Блок Choice гарантирует, что будет использоваться только одно из входящих сообщений.

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ISource](isource-class.md)

`choice`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept"></a>гласит

Принимает сообщение, предложенное этим блоком `choice`, передавая владение вызывающему объекту.

```cpp
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `accept`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение о том, что вызывающий объект теперь является владельцем.

## <a name="acquire_ref"></a>acquire_ref

Получает число ссылок на этот блок сообщений `choice`, чтобы предотвратить удаление.

```cpp
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Remarks

Этот метод вызывается объектом `ITarget`, который связан с этим источником во время выполнения метода `link_target`.

## <a name="ctor"></a>усмотрени

Создает блок обмена сообщениями `choice` .

```cpp
explicit choice(
    T _Tuple);

choice(
    Scheduler& _PScheduler,
    T _Tuple);

choice(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

choice(
    choice&& _Choice);
```

### <a name="parameters"></a>Параметры

*_Tuple*<br/>
Объект `tuple` источников по выбору.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `choice` .

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `choice` . Используемый объект `Scheduler` подразумевается группой расписаний.

*_Choice*<br/>
Блок обмена сообщениями `choice` , из которого выполняется копирование. Обратите внимание, что исходный объект становится потерянным, превращая этот конструктор в конструктор перемещения.

### <a name="remarks"></a>Remarks

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Конструкция перемещения не выполняется при блокировке. Это означает, что пользователь должен убедиться в отсутствии простых задач во время перемещения. В противном случае могут возникнуть многочисленные гонки, приводящие к исключениям или недопустимому состоянию.

## <a name="dtor"></a>~ Choice

Уничтожает блок сообщений `choice`.

```cpp
~choice();
```

## <a name="consume"></a>потребляющие

Использует сообщение, которое было ранее предложено этим блоком `choice` сообщений и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.

```cpp
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
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

## <a name="has_value"></a>has_value

Проверяет, инициализирован ли этот блок обмена сообщениями `choice` с тем же значением.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если блок получил значение; в противном случае — значение **false** .

## <a name="index"></a>номер

Возвращает индекс в `tuple` представляющий элемент, выбранный `choice` блоком обмена сообщениями.

```cpp
size_t index();
```

### <a name="return-value"></a>Возвращаемое значение

Индекс сообщения.

### <a name="remarks"></a>Remarks

Полезные данные сообщения можно извлечь с помощью метода `get`.

## <a name="link_target"></a>link_target

Связывает целевой блок с этим блоком сообщений `choice`.

```cpp
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на блок `ITarget`, связываемый с этим блоком сообщений `choice`.

## <a name="release"></a>отпускании

Освобождает предыдущее успешное резервирование сообщения.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` освобожденного объекта `message`.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `release`.

## <a name="release_ref"></a>release_ref

Освобождает счетчик ссылок на этом `choice` блоке сообщений.

```cpp
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Remarks

Этот метод вызывается объектом `ITarget`, связь с которым удаляется из этого источника. Блоку источника разрешено освобождать все ресурсы, зарезервированные для целевого блока.

## <a name="reserve"></a>предназначен

Резервирует сообщение, которое было предложено этим блоком `choice` Messaging.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` резервируемого объекта `message`.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `reserve`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если сообщение было успешно зарезервировано; в противном случае — **значение false** . Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.

### <a name="remarks"></a>Remarks

После вызова `reserve`, если он выполняется, необходимо вызвать метод `consume` или `release`, чтобы получить или предоставить право на владение сообщениями соответственно.

## <a name="unlink_target"></a>unlink_target

Отменяет связь с целевым блоком из этого блока сообщений `choice`.

```cpp
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на блок `ITarget`, который нужно удалить из этого `choice` блока обмена сообщениями.

## <a name="unlink_targets"></a>unlink_targets

Отменяет связь со всеми целевыми объектами из этого блока сообщений `choice`.

```cpp
virtual void unlink_targets();
```

### <a name="remarks"></a>Remarks

Этот метод не требуется вызывать из деструктора, так как деструктор для внутреннего блока `single_assignment` будет иметь правильную связь.

## <a name="value"></a>значений

Возвращает сообщение, чей индекс был выбран блоком сообщений `choice`.

```cpp
template <
    typename _Payload_type
>
_Payload_type const& value();
```

### <a name="parameters"></a>Параметры

*_Payload_type*<br/>
Тип полезных данных сообщения.

### <a name="return-value"></a>Возвращаемое значение

Полезные данные сообщения.

### <a name="remarks"></a>Remarks

Поскольку блок сообщений `choice` может принимать входные данные с различными типами полезной нагрузки, необходимо указать тип полезной нагрузки в момент извлечения. Тип можно определить на основе результата метода `index`.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс join](join-class.md)<br/>
[Класс single_assignment](single-assignment-class.md)
