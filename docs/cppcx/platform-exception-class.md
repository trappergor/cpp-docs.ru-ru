---
title: Класс Platform::Exception
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception::Exception
- VCCORLIB/Platform::Exception::CreateException
- VCCORLIB/Platform::Exception::HResult
- VCCORLIB/Platform::Exception::Message
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
ms.openlocfilehash: d37d55c56e3c23d8d9129c985cb4272d2e3ee47a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368738"
---
# <a name="platformexception-class"></a>Класс Platform::Exception

Представляет ошибки, происходящие во время выполнения приложения. Пользовательские классы исключений не могут быть производными от класса `Platform::Exception`. Если требуется пользовательское исключение, можно использовать класс `Platform::COMException` и указать относящееся к приложению значение HRESULT.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class Exception : Object,    IException,    IPrintable,    IEquatable
```

### <a name="members"></a>Участники

Класс `Exception` наследуется от класса `Object` и интерфейсов `IException`, `IPrintable`и `IEquatable` .

Класс `Exception` имеет также следующие типы членов.

### <a name="constructors"></a>Конструкторы

|Член|Описание|
|------------|-----------------|
|[Exception::Exception](#ctor)|Инициализирует новый экземпляр класса `Exception`.|

### <a name="methods"></a>Методы

Класс `Exception` наследует методы `Equals()`, `Finalize()`,`GetHashCode()`,`GetType()`,`MemberwiseClose()`и `ToString()` из [Platform::Object Class](../cppcx/platform-object-class.md). Класс `Exception` содержит также следующий метод.

|Член|Описание|
|------------|-----------------|
|[Exception::CreateException](#createexception)|Создает исключение, представляющее указанное значение HRESULT.|

### <a name="properties"></a>Свойства

Класс Exception также содержит следующие свойства.

|Член|Описание|
|------------|-----------------|
|[Exception::HRESULT](#hresult)|Значение HRESULT, соответствующее исключению.|
|[Exception::Message](#message)|Сообщение с описанием исключения. Это значение доступно только для чтения, его нельзя изменить после создания `Exception` .|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="createexception"></a> Метод Exception::CreateException

Создает Platform::Exception^ из указанного значения HRESULT.

### <a name="syntax"></a>Синтаксис

```cpp
Exception^ CreateException(int32 hr);
Exception^ CreateException(int32 hr, Platform::String^ message);
```

### <a name="parameters"></a>Параметры

*hr*<br/>
Значение HRESULT, которое, как правило, получается из вызова метода COM. Если значение равно 0, что эквивалентно S_OK, этот метод вызывает исключение [Platform::InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md) поскольку методы COM, которые завершились успешно, не должны вызывать исключения.

*message*<br/>
Строка с описанием ошибки.

### <a name="return-value"></a>Возвращаемое значение

Исключение, представляющее HRESULT ошибки.

### <a name="remarks"></a>Примечания

Используйте этот метод для создания исключения из значения HRESULT, возвращаемого, например, из вызова интерфейса COM. Можно использовать перегруженный метод, принимающий параметр String^, чтобы предоставить пользовательское сообщение.

Настоятельно рекомендуется использовать CreateException для создания строго типизированного исключения вместо создания [Platform::COMException](../cppcx/platform-comexception-class.md) который просто содержит значение HRESULT.

## <a name="ctor"></a>  Конструктор Exception::Exception

Инициализирует новый экземпляр класса Exception.

### <a name="syntax"></a>Синтаксис

```cpp
Exception(int32 hresult);
Exception(int32 hresult, ::Platform::String^ message);
```

### <a name="parameters"></a>Параметры

*hresult*<br/>
HRESULT ошибки, представляемый этим исключением.

*message*<br/>
Задаваемое пользователем сообщение (например, текст рекомендаций), связанное с исключением. В общем случае следует выбирать вторую перегрузку, чтобы предоставить максимально подробное описание того, как и почему произошла конкретная ошибка.

## <a name="hresult"></a>  Свойство Exception::HRESULT

Значение HRESULT, соответствующее исключению.

### <a name="syntax"></a>Синтаксис

```cpp
public:
    property int HResult { int get(); }
```

## <a name="property-value"></a>Значение свойства

Значение HRESULT.

### <a name="remarks"></a>Примечания

Большинство исключений создаются как ошибки модели COM, которые возвращаются в виде значений HRESULT. C++/CX преобразует эти значения в объекты Platform::Exception^, и это свойство сохраняет значение исходного кода ошибки.

## <a name="message"></a> Свойство Exception::Message

Сообщение с описанием ошибки.

### <a name="syntax"></a>Синтаксис

```cpp
public:property String^ Message;
```

## <a name="property-value"></a>Значение свойства

В исключениях, создаваемых в среде выполнения Windows, это предоставляемое системой описание ошибки.

### <a name="remarks"></a>Примечания

В Windows 8 это свойство доступно только для чтения, так как исключения в этой версии среды выполнения Windows передаются через интерфейс ABI только в качестве значения HRESULT. В Windows 8.1 через интерфейс ABI передается более подробная информация об исключениях, и можно задать пользовательское сообщение, к которому другие компоненты могут обращаться программным образом. Дополнительные сведения см. в разделе [исключения (C++/CX)](../cppcx/exceptions-c-cx.md).

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
