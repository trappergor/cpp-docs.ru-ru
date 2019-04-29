---
title: Класс Platform::COMException
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::COMException
- VCCORLIB/Platform::Exception::HResult
- VCCORLIB/Platform::Exception::Message
helpviewer_keywords:
- Platform::COMException Class
ms.assetid: 44fda4e5-574f-4d12-ab5f-4ff3f277448d
ms.openlocfilehash: 5a74184a8cbc4126988da2ba0be61d9f5b2bb71c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383351"
---
# <a name="platformcomexception-class"></a>Класс Platform::COMException

Представляет ошибки COM, возникающие при выполнении приложения. COMException — базовый класс для набора предопределенных стандартных исключений.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class COMException : Exception,    IException,    IPrintable,    IEquatable
```

### <a name="members"></a>Участники

Класс COMException наследует от класса Object и интерфейсов IException, IPrintable и IEquatable.

Класс COMException также имеет следующие типы членов.

**Конструкторы**

|Член|Описание|
|------------|-----------------|
|[COMException](#ctor)|Инициализирует новый экземпляр класса COMException.|

**Методы**

Класс COMException наследует методы Equals(), Finalize(), GetHashCode(), GetType(), MemberwiseClose() и ToString() от класса [Platform::Object Class](../cppcx/platform-object-class.md).

**Свойства**

Класс COMException имеет следующие свойства.

|Член|Описание|
|------------|-----------------|
|[Exception::HRESULT](#hresult)|Значение HRESULT, соответствующее исключению.|
|[Exception::Message](#message)|Сообщение с описанием исключения.|

## <a name="derived-exceptions"></a>Производные исключения

Следующие предопределенные исключения наследуются от класса COMException. Они отличаются от класса COMException только своими именами, именами своих конструкторов и значениями HRESULT.

|name|Значение HRESULT|Описание|
|----------|------------------------|-----------------|
|COMException|*Определяемое пользователем значение hresult*|Возникает при возвращении неизвестного значения HRESULT после вызова метода COM.|
|AccessDeniedException|E_ACCESSDENIED|Возникает при запрете доступа к ресурсу или функции.|
|ChangedStateException|E_CHANGED_STATE|Возникает, если метод итератора коллекции или представления коллекции вызван после изменения родительской коллекции, что делает результаты метода недействительными.|
|ClassNotRegisteredException|REGDB_E_CLASSNOTREG|Возникает, если COM-класс не зарегистрирован.|
|DisconnectedException|RPC_E_DISCONNECTED|Возникает, если объект отключен от своих клиентов.|
|FailureException|E_FAIL|Возникает, если операция завершается неудачно.|
|InvalidArgumentException|E_INVALIDARG|Вызывается, если один из передаваемых методу аргументов является недопустимым.|
|InvalidCastException|E_NOINTERFACE|Возникает, если тип не удается привести к другому типу.|
|NotImplementedException|E_NOTIMPL|Возникает, если метод интерфейса не реализован в классе.|
|NullReferenceException|E_POINTER|Возникает при попытке разыменовать ссылку на объект NULL.|
|OperationCanceledException|E_ABORT|Возникает при отмене операции.|
|OutOfBoundsException|E_BOUNDS|Возникает, когда операция пытается получить доступ к данным за пределами допустимого диапазона.|
|OutOfMemoryException|E_OUTOFMEMORY|Возникает, если недостаточно памяти для выполнения операции.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="ctor"></a> Конструктор COMException::COMException

Инициализирует новый экземпляр класса COMException.

### <a name="syntax"></a>Синтаксис

```cpp
COMException( int hresult )
```

### <a name="parameters"></a>Параметры

*hresult*<br/>
HRESULT ошибки, представляемый этим исключением.

## <a name="hresult"></a> COMException::HRESULT-свойство

Значение HRESULT, соответствующее исключению.

### <a name="syntax"></a>Синтаксис

```cpp
public:
    property int HResult { int get();}
```

## <a name="property-value"></a>Значение свойства

Значение HRESULT, задающее ошибку.

### <a name="remarks"></a>Примечания

Дополнительные сведения об интерпретации значения HRESULT см. в разделе [структуры из кодов ошибок модели COM](/windows/desktop/com/structure-of-com-error-codes).

## <a name="message"></a> COMException::Message-свойство

Сообщение с описанием исключения.

### <a name="syntax"></a>Синтаксис

```cpp
public:property String^ Message {    String^ get();}
```

### <a name="property-value"></a>Значение свойства

Описание исключения.

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
