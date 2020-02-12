---
title: Класс ISource
ms.date: 11/04/2016
f1_keywords:
- ISource
- AGENTS/concurrency::ISource
- AGENTS/concurrency::ISource::accept
- AGENTS/concurrency::ISource::acquire_ref
- AGENTS/concurrency::ISource::consume
- AGENTS/concurrency::ISource::link_target
- AGENTS/concurrency::ISource::release
- AGENTS/concurrency::ISource::release_ref
- AGENTS/concurrency::ISource::reserve
- AGENTS/concurrency::ISource::unlink_target
- AGENTS/concurrency::ISource::unlink_targets
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
ms.openlocfilehash: a9ef9990db6376536f2f2a15c053b3b1d4ed12cf
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139321"
---
# <a name="isource-class"></a>Класс ISource

Класс `ISource` является интерфейсом для всех блоков источников. Блоки источников распространяют сообщения в блоки `ITarget`.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class ISource;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных полезной нагрузки в сообщениях, создаваемых исходным блоком.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Description|
|----------|-----------------|
|`source_type`|Псевдоним типа для `T`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Деструктор "~ ISource"](#dtor)|Уничтожает объект `ISource`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[гласит](#accept)|При переопределении в производном классе принимает сообщение, которое было предложено этим блоком `ISource`, передавая владение вызывающему объекту.|
|[acquire_ref](#acquire_ref)|При переопределении в производном классе получает счетчик ссылок на этот блок `ISource`, чтобы предотвратить удаление.|
|[consume](#consume)|При переопределении в производном классе использует сообщение, которое было ранее предложено этим блоком `ISource` и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[link_target](#link_target)|При переопределении в производном классе связывает целевой блок с этим блоком `ISource`.|
|[release](#release)|При переопределении в производном классе освобождает предыдущее успешное резервирование сообщения.|
|[release_ref](#release_ref)|При переопределении в производном классе освобождает счетчик ссылок на этот блок `ISource`.|
|[reserve](#reserve)|При переопределении в производном классе резервирует сообщение, которое ранее было предложено этим блоком `ISource`.|
|[unlink_target](#unlink_target)|При переопределении в производном классе отменяет связь целевого блока с этим блоком `ISource`, если он ранее был связан.|
|[unlink_targets](#unlink_targets)|При переопределении в производном классе отменяет связь всех целевых блоков с этим блоком `ISource`.|

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISource`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept"></a>гласит

При переопределении в производном классе принимает сообщение, которое было предложено этим блоком `ISource`, передавая владение вызывающему объекту.

```cpp
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `accept`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение о том, что вызывающий объект теперь является владельцем.

### <a name="remarks"></a>Remarks

Метод `accept` вызывается целевым объектом, в то время как сообщение предлагается этим блоком `ISource`. Возвращаемый указатель на сообщение может отличаться от переданного в метод `propagate` блока `ITarget`, если этот источник решит создать копию сообщения.

## <a name="acquire_ref"></a>acquire_ref

При переопределении в производном классе получает счетчик ссылок на этот блок `ISource`, чтобы предотвратить удаление.

```cpp
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Remarks

Этот метод вызывается объектом `ITarget`, который связан с этим источником во время выполнения метода `link_target`.

## <a name="consume"></a>потребляющие

При переопределении в производном классе использует сообщение, которое было ранее предложено этим блоком `ISource` и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.

```cpp
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
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

## <a name="dtor"></a>~ ISource

Уничтожает объект `ISource`.

```cpp
virtual ~ISource();
```

## <a name="link_target"></a>link_target

При переопределении в производном классе связывает целевой блок с этим блоком `ISource`.

```cpp
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, связанный с этим блоком `ISource`.

## <a name="release"></a>отпускании

При переопределении в производном классе освобождает предыдущее успешное резервирование сообщения.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` зарезервированного объекта `message`.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `release`.

## <a name="release_ref"></a>release_ref

При переопределении в производном классе освобождает счетчик ссылок на этот блок `ISource`.

```cpp
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Remarks

Этот метод вызывается объектом `ITarget`, связь с которым удаляется из этого источника. Блоку источника разрешено освобождать все ресурсы, зарезервированные для целевого блока.

## <a name="reserve"></a>предназначен

При переопределении в производном классе резервирует сообщение, которое ранее было предложено этим блоком `ISource`.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity` предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий метод `reserve`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если сообщение было успешно зарезервировано; в противном случае — **значение false** . Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.

### <a name="remarks"></a>Remarks

После вызова `reserve`, если он выполняется, необходимо вызвать метод `consume` или `release`, чтобы получить или предоставить право на владение сообщениями соответственно.

## <a name="unlink_target"></a>unlink_target

При переопределении в производном классе отменяет связь целевого блока с этим блоком `ISource`, если он ранее был связан.

```cpp
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, связь с которым выполняется из этого блока `ISource`.

## <a name="unlink_targets"></a>unlink_targets

При переопределении в производном классе отменяет связь всех целевых блоков с этим блоком `ISource`.

```cpp
virtual void unlink_targets() = 0;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс ITarget](itarget-class.md)
