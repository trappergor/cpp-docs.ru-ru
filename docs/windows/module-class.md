---
title: Класс модуля | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
- module/Microsoft::WRL::Module::Create
- module/Microsoft::WRL::Module::DecrementObjectCount
- module/Microsoft::WRL::Module::GetActivationFactory
- module/Microsoft::WRL::Module::GetClassObject
- module/Microsoft::WRL::Module::GetModule
- module/Microsoft::WRL::Module::GetObjectCount
- module/Microsoft::WRL::Module::IncrementObjectCount
- module/Microsoft::WRL::Module::Module
- module/Microsoft::WRL::Module::objectCount_Data
- module/Microsoft::WRL::Module::RegisterCOMObject
- module/Microsoft::WRL::Module::RegisterObjects
- module/Microsoft::WRL::Module::RegisterWinRTObject
- module/Microsoft::WRL::Module::releaseNotifier_
- module/Microsoft::WRL::Module::Terminate
- module/Microsoft::WRL::Module::~Module
- module/Microsoft::WRL::Module::UnregisterCOMObject
- module/Microsoft::WRL::Module::UnregisterObjects
- module/Microsoft::WRL::Module::UnregisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Module class
- Microsoft::WRL::Module::Create method
- Microsoft::WRL::Module::DecrementObjectCount method
- Microsoft::WRL::Module::GetActivationFactory method
- Microsoft::WRL::Module::GetClassObject method
- Microsoft::WRL::Module::GetModule method
- Microsoft::WRL::Module::GetObjectCount method
- Microsoft::WRL::Module::IncrementObjectCount method
- Microsoft::WRL::Module::Module, constructor
- Microsoft::WRL::Module::objectCount_ data member
- Microsoft::WRL::Module::RegisterCOMObject method
- Microsoft::WRL::Module::RegisterObjects method
- Microsoft::WRL::Module::RegisterWinRTObject method
- Microsoft::WRL::Module::releaseNotifier_ data member
- Microsoft::WRL::Module::Terminate method
- Microsoft::WRL::Module::~Module, destructor
- Microsoft::WRL::Module::UnregisterCOMObject method
- Microsoft::WRL::Module::UnregisterObjects method
- Microsoft::WRL::Module::UnregisterWinRTObject method
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2357790e3084c91011f16eb9f1f718948462f898
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059484"
---
# <a name="module-class"></a>Module - класс

Представляет коллекцию связанных объектов.

## <a name="syntax"></a>Синтаксис

```cpp
template<ModuleType moduleType>
class Module;

template<>
class Module<InProc> : public Details::ModuleBase;

template<>
class Module<OutOfProc> : public Module<InProc>;
```

### <a name="parameters"></a>Параметры

*Тип модуля*<br/>
Сочетание одного или нескольких [ModuleType](../windows/moduletype-enumeration.md) значений перечисления.

## <a name="members"></a>Участники

### <a name="protected-classes"></a>Защищенные классы

name                                                                                | Описание
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[Module::GenericReleaseNotifier](../windows/module-genericreleasenotifier-class.md) | Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается лямбда-выражением, функтором или указателем на функцию.
[Module::MethodReleaseNotifier](../windows/module-methodreleasenotifier-class.md)   | Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий заданного объекта и ее члена указатель на метод.
[Module::ReleaseNotifier](../windows/module-releasenotifier-class.md)               | Вызывает обработчик событий при освобождении последнего объекта в модуле.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                             | Описание
-------------------------------- | -----------------------------------------------------------
[Модуль:: ~ Module](#tilde-module) | Деинициализирует текущий экземпляр `Module` класса.

### <a name="protected-constructors"></a>Защищенные конструкторы

Имя                      | Описание
------------------------- | ---------------------------------------------------
[Module::module](#module) | Инициализирует новый экземпляр класса `Module`.

### <a name="public-methods"></a>Открытые методы

Имя                                                    | Описание
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[Module::CREATE](#create)                               | Создает экземпляр модуля.
[Module::DecrementObjectCount](#decrementobjectcount)   | Уменьшает число объектов, отслеживаемых модулем.
[Module::GetActivationFactory](#getactivationfactory)   | Получает фабрику активации для модуля.
[Module::GetClassObject](#getclassobject)               | Извлекает кэш фабрик классов.
[Module::GetModule](#getmodule)                         | Создает экземпляр модуля.
[Module::GetObjectCount](#getobjectcount)               | Извлекает количество объектов, управляемых этим модулем.
[Module::IncrementObjectCount](#incrementobjectcount)   | Увеличивает число объектов, отслеживаемых модулем.
[Module::RegisterCOMObject](#registercomobject)         | Регистрирует один или несколько объектов модели COM, чтобы другие приложения могли к ним подключиться.
[Module::RegisterObjects](#registerobjects)             | Регистрирует объекты COM или среду выполнения Windows, чтобы другие приложения могли подключиться к ним.
[Module::RegisterWinRTObject](#registerwinrtobject)     | Регистрирует один или несколько объектов среды выполнения Windows, чтобы другие приложения могли подключиться к ним.
[Module::Terminate](#terminate)                         | Приводит к завершению работы всех экземпляров фабрик, созданных модулем.
[Module::UnregisterCOMObject](#unregistercomobject)     | Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.
[Module::UnregisterObjects](#unregisterobjects)         | Отменяет регистрацию объектов в указанном модуле. Таким образом другие приложения не смогут подключиться к ним.
[Module::UnregisterWinRTObject](#unregisterwinrtobject) | Отменяет регистрацию одного или нескольких объектов среды выполнения Windows, таким образом, чтобы другие приложения не смогут подключиться к ним.

### <a name="protected-methods"></a>Защищенные методы

Имя                      | Описание
------------------------- | --------------------------------
[Module::CREATE](#create) | Создает экземпляр модуля.

### <a name="protected-data-members"></a>Защищенные члены данных

name                                         | Описание
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[Module::objectCount_](#objectcount)         | Следит за сколько классы были созданы при помощи [сделать](../windows/make-function.md) функции.
[Module::releaseNotifier_](#releasenotifier) | Содержит указатель на `ReleaseNotifier` объект.

### <a name="macros"></a>Макросы

Имя | Описание------| --- [ActivatableClass](../windows/activatableclass-macros.md) |  Заполняет внутренний кэш, содержащий фабрику, можно создать экземпляр указанного класса. Этот макрос задает параметры идентификатора фабрики и группы по умолчанию.
[ActivatableClassWithFactory](../windows/activatableclass-macros.md) | Заполняет внутренний кэш, содержащий фабрику, можно создать экземпляр указанного класса. Этот макрос можно указать параметр конкретной фабрике.
[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) | Заполняет внутренний кэш, содержащий фабрику, можно создать экземпляр указанного класса. Этот макрос можно задать такие параметры идентификатора группы и конкретной фабрике.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="tilde-module"></a>Модуль:: ~ Module

Деинициализирует текущий экземпляр `Module` класса.

```cpp
virtual ~Module();
```

## <a name="create"></a>Module::CREATE

Создает экземпляр модуля.

```cpp
WRL_NOTHROW static Module& Create();
template<typename T>
WRL_NOTHROW static Module& Create(
   T callback
);
template<typename T>
WRL_NOTHROW static Module& Create(
   _In_ T* object,
   _In_ void (T::* method)()
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип модуля.

*обратный вызов*<br/>
Вызывается при освобождении последнего объекта экземпляр модуля.

*object*<br/>
*Объект* и *метод* параметры используются в сочетании. Указывает на последний объект экземпляра при освобождении последнего объекта экземпляра в модуле.

*Метод*<br/>
*Объект* и *метод* параметры используются в сочетании. Указывает метод последнего экземпляра объекта при освобождении последнего объекта экземпляра в модуле.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на модуль.

## <a name="decrementobjectcount"></a>Module::DecrementObjectCount

Уменьшает число объектов, отслеживаемых модулем.

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число, прежде чем операция уменьшения.

## <a name="getactivationfactory"></a>Module::GetActivationFactory

Получает фабрику активации для модуля.

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Параметры

*pActivatibleClassId*<br/>
Представляет IID класса среды выполнения.

*ppIFactory*<br/>
Представляет интерфейс IActivationFactory указанного класса среды выполнения.

*Имя_сервера*<br/>
Имя подмножества фабрик класса в текущем модуле. Укажите имя сервера, используемое в [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) макрос, или указать `nullptr` для получения имени сервера по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, возвращаемое GetActivationFactory.

## <a name="getclassobject"></a>Module::GetClassObject

Извлекает кэш фабрик классов.

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
Идентификатор класса.

*riid*<br/>
Запрошенный идентификатор интерфейса.

*ppv*<br/>
Указатель на возвращаемый объект.

*Имя_сервера*<br/>
Имя сервера, указанное в макросе `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx` или `ActivatableClass`; в противном случае — значение `nullptr` для получения имени сервера по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Этот метод можно используйте только для модели COM, а не среду выполнения Windows. Этот метод предоставляет только `IClassFactory` методы.

## <a name="getmodule"></a>Module::GetModule

Создает экземпляр модуля.

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на модуль.

## <a name="getobjectcount"></a>Module::GetObjectCount

Извлекает количество объектов, управляемых этим модулем.

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее количество объектов, управляемых этим модулем.

## <a name="incrementobjectcount"></a>Module::IncrementObjectCount

Увеличивает число объектов, отслеживаемых модулем.

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>Возвращаемое значение

Счетчик перед выполнением операции инкремента.

## <a name="module"></a>Module::module

Инициализирует новый экземпляр класса `Module`.

```cpp
Module();
```

### <a name="remarks"></a>Примечания

Этот конструктор является защищенным и не может быть вызван ключевым словом `new`. Вместо этого вызовите [Module::GetModule](#getmodule) или [Module::Create](#create).

## <a name="objectcount"></a>Module::objectCount_

Следит за сколько классы были созданы при помощи [сделать](../windows/make-function.md) функции.

```cpp
volatile long objectCount_;
```

## <a name="registercomobject"></a>Module::RegisterCOMObject

Регистрирует один или несколько объектов модели COM, чтобы другие приложения могли к ним подключиться.

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);

```

### <a name="parameters"></a>Параметры

*Имя_сервера*<br/>
Полное имя сервера.

*идентификаторов CLSID*<br/>
Массив регистрируемых идентификаторов CLSID.

*фабрики*<br/>
Массив интерфейсов IUnknown объектов класса, чья доступность публикуется.

*Файлы cookie*<br/>
После завершения операции представляет массив указателей на значения, которые определяют зарегистрированные объекты класса. Эти значения в дальнейшем используются для отмены регистрации.

*count*<br/>
Количество идентификаторов CLSID, которые необходимо зарегистрировать.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT (например, CO_E_OBJISREG), указывающее причину неудачного завершения операции.

### <a name="remarks"></a>Примечания

COM-объекты зарегистрированы с помощью перечислителя CLSCTX_LOCAL_SERVER перечисления CLSCTX.

Тип подключения к зарегистрированным объектам определяется сочетание текущего *comflag* параметр шаблона и перечислителя REGCLS_SUSPENDED перечисления.

## <a name="registerobjects"></a>Module::RegisterObjects

Регистрирует объекты COM или среду выполнения Windows, чтобы другие приложения могли подключиться к ним.

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Параметры

*module*<br/>
Массив объектов COM или среду выполнения Windows.

*Имя_сервера*<br/>
Имя сервера, который создал объекты.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="registerwinrtobject"></a>Module::RegisterWinRTObject

Регистрирует один или несколько объектов среды выполнения Windows, чтобы другие приложения могли подключиться к ним.

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>Параметры

*Имя_сервера*<br/>
Имя, которое определяет подмножество объектов, затронутых этой операцией.

*activatableClassIds*<br/>
Массив активируемых идентификаторов CLSID для регистрации.

*Файл cookie*<br/>
Значение, которое идентифицирует зарегистрированные объекты класса. Это значение в дальнейшем используется для отмены регистрации.

*count*<br/>
Количество объектов, которое необходимо зарегистрировать.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT (например, CO_E_OBJISREG), указывающее причину неудачного завершения операции.

## <a name="releasenotifier"></a>Module::releaseNotifier_

Содержит указатель на `ReleaseNotifier` объект.

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="terminate"></a>Module::Terminate

Приводит к завершению работы всех экземпляров фабрик, созданных модулем.

```cpp
void Terminate();
```

### <a name="remarks"></a>Примечания

Освобождает фабрики в кэше.

## <a name="unregistercomobject"></a>Module::UnregisterCOMObject

Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>Параметры

*Имя_сервера*<br/>
(Не используется)

*Файлы cookie*<br/>
Массив указателей на значения, которые идентифицируют объекты класса для отмены регистрации. Массив был создан с [RegisterCOMObject](#registercomobject) метод.

*count*<br/>
Количество классов для отмены регистрации.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="unregisterobjects"></a>Module::UnregisterObjects

Отменяет регистрацию объектов в указанном модуле. Таким образом другие приложения не смогут подключиться к ним.

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Параметры

*module*<br/>
Указатель на модуль.

*Имя_сервера*<br/>
Представляет имя, которое определяет подмножество объектов, затронутых этой операцией.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="unregisterwinrtobject"></a>Module::UnregisterWinRTObject

Отменяет регистрацию одного или нескольких объектов среды выполнения Windows, таким образом, чтобы другие приложения не смогут подключиться к ним.

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>Параметры

*Файл cookie*<br/>
Указатель на значение, определяющее объект класса, регистрация которого должна быть отменена.
