---
title: Класс ITarget
ms.date: 11/04/2016
f1_keywords:
- ITarget
- AGENTS/concurrency::ITarget
- AGENTS/concurrency::ITarget::propagate
- AGENTS/concurrency::ITarget::send
- AGENTS/concurrency::ITarget::supports_anonymous_source
- AGENTS/concurrency::ITarget::link_source
- AGENTS/concurrency::ITarget::unlink_source
- AGENTS/concurrency::ITarget::unlink_sources
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
ms.openlocfilehash: dc9eacad744536e640417a4ebf51b975bd05bcc7
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142034"
---
# <a name="itarget-class"></a>Класс ITarget

Класс `ITarget` является интерфейсом для всех целевых блоков. Целевые блоки потребляют сообщения, предлагаемые ими блоками `ISource`.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class ITarget;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных полезной нагрузки в сообщениях, принимаемых целевым блоком.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Description|
|----------|-----------------|
|`filter_method`|Сигнатура любого метода, используемого блоком, который возвращает значение `bool`, чтобы определить, следует ли принять предложенное сообщение.|
|`type`|Псевдоним типа для `T`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Деструктор ~ ITarget](#dtor)|Уничтожает объект `ITarget`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[распространения](#propagate)|При переопределении в производном классе асинхронно передает сообщение из исходного блока в этот целевой блок.|
|[send](#send)|При переопределении в производном классе синхронно передает сообщение в целевой блок.|
|[supports_anonymous_source](#supports_anonymous_source)|При переопределении в производном классе возвращает значение true или false в зависимости от того, принимает ли блок сообщений сообщения, предоставляемые не связанным с ним источником. Если переопределенный метод возвращает **значение true**, целевой объект не может отложить предлагаемое сообщение, так как в дальнейшем для использования отложенного сообщения потребуется определить источник в реестре его исходной ссылки.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[link_source](#link_source)|При переопределении в производном классе связывает указанный блок источника с этим блоком `ITarget`.|
|[unlink_source](#unlink_source)|При переопределении в производном классе отменяет связь указанного исходного блока с этим блоком `ITarget`.|
|[unlink_sources](#unlink_sources)|При переопределении в производном классе отменяет связь всех исходных блоков с этим блоком `ITarget`.|

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ITarget`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="dtor"></a>~ ITarget

Уничтожает объект `ITarget`.

```cpp
virtual ~ITarget();
```

## <a name="link_source"></a>link_source

При переопределении в производном классе связывает указанный блок источника с этим блоком `ITarget`.

```cpp
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Параметры

*_PSource*<br/>
Блок `ISource`, связанный с этим блоком `ITarget`.

### <a name="remarks"></a>Remarks

Эта функция не должна вызываться напрямую в блоке `ITarget`. Блоки должны быть соединены друг с другом с помощью метода `link_target` в блоках `ISource`, которые вызывают метод `link_source` для соответствующего целевого объекта.

## <a name="propagate"></a>распространения

При переопределении в производном классе асинхронно передает сообщение из исходного блока в этот целевой блок.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если параметр `_PMessage` или `_PSource` имеет значение `NULL`.

## <a name="send"></a>Отправить

При переопределении в производном классе синхронно передает сообщение в целевой блок.

```cpp
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если параметр `_PMessage` или `_PSource` имеет значение `NULL`.

Использование метода `send` за пределами инициации сообщений и распространения сообщений в сети опасно и может привести к взаимоблокировке.

Когда `send` возвращает значение, сообщение уже было принято и передано в целевой блок или было отклонено целевым объектом.

## <a name="supports_anonymous_source"></a>supports_anonymous_source

При переопределении в производном классе возвращает значение true или false в зависимости от того, принимает ли блок сообщений сообщения, предоставляемые не связанным с ним источником. Если переопределенный метод возвращает **значение true**, целевой объект не может отложить предлагаемое сообщение, так как в дальнейшем для использования отложенного сообщения потребуется определить источник в его реестре ссылок саурсе.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если блок может принимать сообщение от источника, который не связан с ним. в противном случае — значение **false** .

## <a name="unlink_source"></a>unlink_source

При переопределении в производном классе отменяет связь указанного исходного блока с этим блоком `ITarget`.

```cpp
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Параметры

*_PSource*<br/>
В этом блоке `ITarget` отменяется связь `ISource` блока.

### <a name="remarks"></a>Remarks

Эта функция не должна вызываться напрямую в блоке `ITarget`. Блоки должны быть отключены с помощью методов `unlink_target` или `unlink_targets` в блоках `ISource`, которые будут вызывать метод `unlink_source` для соответствующего целевого объекта.

## <a name="unlink_sources"></a>unlink_sources

При переопределении в производном классе отменяет связь всех исходных блоков с этим блоком `ITarget`.

```cpp
virtual void unlink_sources() = 0;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс ISource](isource-class.md)
