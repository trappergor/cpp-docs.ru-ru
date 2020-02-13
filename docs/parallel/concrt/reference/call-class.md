---
title: Класс call
ms.date: 11/04/2016
f1_keywords:
- call
- AGENTS/concurrency::call
- AGENTS/concurrency::call::call
- AGENTS/concurrency::call::process_input_messages
- AGENTS/concurrency::call::process_message
- AGENTS/concurrency::call::propagate_message
- AGENTS/concurrency::call::send_message
- AGENTS/concurrency::call::supports_anonymous_source
helpviewer_keywords:
- call class
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
ms.openlocfilehash: 445e368ced9d9c8faf30351ecaeecc4e1b8a59f2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142838"
---
# <a name="call-class"></a>Класс call

Блок обмена сообщениями `call` — это упорядоченный блок `target_block` с несколькими источниками, который вызывает заданную функцию при получении сообщения.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезных данных сообщений, распространяемых в этот блок.

*_FunctorType*<br/>
Сигнатура функций, которые может принимать этот блок.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[обращение](#ctor)|Перегружен. Создает блок обмена сообщениями `call` .|
|[Деструктор вызова ~](#dtor)|Уничтожает блок сообщений `call`.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[process_input_messages](#process_input_messages)|Выполняет функцию Call для входных сообщений.|
|[process_message](#process_message)|Обрабатывает сообщение, которое было принято этим блоком сообщений `call`.|
|[propagate_message](#propagate_message)|Асинхронно передает сообщение из блока `ISource` в этот `call` блок сообщений. Вызывается методом `propagate` при вызове из исходного блока.|
|[send_message](#send_message)|Синхронно передает сообщение из блока `ISource` в этот `call` блок сообщений. Вызывается методом `send` при вызове из исходного блока.|
|[supports_anonymous_source](#supports_anonymous_source)|Переопределяет метод `supports_anonymous_source`, чтобы указать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником. (Переопределяет метод [ITarget:: supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ITarget](itarget-class.md)

[target_block](target-block-class.md)

`call`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="ctor"></a>обращение

Создает блок обмена сообщениями `call` .

```cpp
call(
    _Call_method const& _Func);

call(
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Параметры

*_Func*<br/>
Функция, которая будет вызываться для каждого принятого сообщения.

*_Filter*<br/>
Функция фильтра, которая определяет, следует ли принимать предлагаемые сообщения.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `call` .

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `call` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Remarks

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .

Тип `_Call_method` — это функтор с сигнатурой, `void (T const &)` которая вызывается этим блоком `call` сообщений для обработки сообщения.

Тип `filter_method` — это функтор с сигнатурой `bool (T const &)` который вызывается этим блоком `call` обмена сообщениями, чтобы определить, должно ли оно принимать предложенное сообщение.

## <a name="dtor"></a>~ Call

Уничтожает блок сообщений `call`.

```cpp
~call();
```

## <a name="process_input_messages"></a>process_input_messages

Выполняет функцию Call для входных сообщений.

```cpp
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на сообщение, которое должно быть обработано.

## <a name="process_message"></a>process_message

Обрабатывает сообщение, которое было принято этим блоком сообщений `call`.

```cpp
virtual void process_message(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на сообщение, которое должно быть обработано.

## <a name="propagate_message"></a>propagate_message

Асинхронно передает сообщение из блока `ISource` в этот `call` блок сообщений. Вызывается методом `propagate` при вызове из исходного блока.

```cpp
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

## <a name="send_message"></a>send_message

Синхронно передает сообщение из блока `ISource` в этот `call` блок сообщений. Вызывается методом `send` при вызове из исходного блока.

```cpp
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

## <a name="supports_anonymous_source"></a>supports_anonymous_source

Переопределяет метод `supports_anonymous_source`, чтобы указать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , поскольку блок не откладывает предлагаемые сообщения.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс transformer](transformer-class.md)
