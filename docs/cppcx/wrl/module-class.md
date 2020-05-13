---
title: Module - класс
ms.date: 10/18/2018
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
ms.openlocfilehash: afd2edacefdf5d62b50a03c0a8c37f13ee5d9c9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371315"
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

*модульType*<br/>
Комбинация одного или нескольких значений перечисления [ModuleType.](moduletype-enumeration.md)

## <a name="members"></a>Участники

### <a name="protected-classes"></a>Защищенные классы

Имя                                                                                | Описание
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[Модуль::GenericReleaseНофикер](module-genericreleasenotifier-class.md) | Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается лямбда-выражением, функтором или указателем на функцию.
[Модуль:MethodReleaseNotifier](module-methodreleasenotifier-class.md)   | Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик события определяется объектом и его элементом указателя на метод.
[Модуль:ReleaseNotifier](module-releasenotifier-class.md)               | Вызывает обработчик событий при освобождении последнего объекта в модуле.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                             | Описание
-------------------------------- | -----------------------------------------------------------
[Модуль:::Модуль](#tilde-module) | Деприиратизирует текущий `Module` экземпляр класса.

### <a name="protected-constructors"></a>Защищенные конструкторы

Имя                      | Описание
------------------------- | ---------------------------------------------------
[Модуль::Модуль](#module) | Инициализирует новый экземпляр класса `Module`.

### <a name="public-methods"></a>Открытые методы

Имя                                                    | Описание
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[Модуль::Создание](#create)                               | Создает экземпляр модуля.
[Модуль::DecrementObjectCount](#decrementobjectcount)   | Декретирует количество объектов, отслеживаемых модулем.
[Модуль::GetActivationFactory](#getactivationfactory)   | Получает фабрику активации для модуля.
[Модуль::GetClassObject](#getclassobject)               | Извлекает кэш фабрик класса.
[Модуль::GetModule](#getmodule)                         | Создает экземпляр модуля.
[Модуль::GetObjectCount](#getobjectcount)               | Извлекает количество объектов, управляемых этим модулем.
[Модуль::ИнкрементныйОбъективКтом](#incrementobjectcount)   | Приравливки количество объектов, отслеживаемых модулем.
[Модуль::RegisterCOMObject](#registercomobject)         | Регистрирует один или несколько объектов модели COM, чтобы другие приложения могли к ним подключиться.
[Модуль:РегистрацияОбъекты](#registerobjects)             | Регистрирует объекты COM или Windows Runtime, чтобы другие приложения могли подключиться к ним.
[Модуль::RegisterWinRTObject](#registerwinrtobject)     | Регистрирует один или несколько объектов Windows Runtime, чтобы другие приложения могли подключиться к ним.
[Модуль::Прекращение](#terminate)                         | Приводит к завершению работы всех экземпляров фабрик, созданных модулем.
[Модуль::UnregisterCOMObject](#unregistercomobject)     | Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.
[Модуль::Нерегистраемыеобъекты](#unregisterobjects)         | Отменяет регистрацию объектов в указанном модуле. Таким образом другие приложения не смогут подключиться к ним.
[Модуль::UnregisterWinRTObject](#unregisterwinrtobject) | Отменить регистрацию одного или нескольких объектов Windows Runtime, чтобы другие приложения не могли подключиться к ним.

### <a name="protected-methods"></a>Защищенные методы

Имя                      | Описание
------------------------- | --------------------------------
[Модуль::Создание](#create) | Создает экземпляр модуля.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                                         | Описание
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[Модуль::objectCount_](#objectcount)         | Отслеживает, сколько классов было создано с функцией [Make.](make-function.md)
[Модуль::releaseNotifier_](#releasenotifier) | Удерживает указатель `ReleaseNotifier` на объект.

### <a name="macros"></a>Макросы

Имя                                                                   | Описание
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ActivatableClass](activatableclass-macros.md)              | Заполняет внутренний кэш, содержащий фабрику, которая может создать экземпляр указанного класса. Этот макрос определяет параметры фабрики по умолчанию и идентификатора группы.
[ActivatableClassWithFactory](activatableclass-macros.md)   | Заполняет внутренний кэш, содержащий фабрику, которая может создать экземпляр указанного класса. Этот макрос позволяет указать определенный параметр завода.
[ActivatableClassWithFactoryEx](activatableclass-macros.md) | Заполняет внутренний кэш, содержащий фабрику, которая может создать экземпляр указанного класса. Этот макрос позволяет указать определенные параметры идентификатора фабрично-заводской и группы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="modulemodule"></a><a name="tilde-module"></a>Модуль:::Модуль

Деприиратизирует текущий `Module` экземпляр класса.

```cpp
virtual ~Module();
```

## <a name="modulecreate"></a><a name="create"></a>Модуль::Создание

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
Вызывается при освобождении объекта последнего экземпляра модуля.

*Объекта*<br/>
Параметры *объекта* и *метода* используются в комбинации. Указывает на объект последнего экземпляра при освобождении объекта последнего экземпляра в модуле.

*method*<br/>
Параметры *объекта* и *метода* используются в комбинации. Указывает на метод объекта последней инстанции при освобождении объекта последнего экземпляра в модуле.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на модуль.

## <a name="moduledecrementobjectcount"></a><a name="decrementobjectcount"></a>Модуль::DecrementObjectCount

Декретирует количество объектов, отслеживаемых модулем.

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>Возвращаемое значение

Подсчет перед операцией по декретуму.

## <a name="modulegetactivationfactory"></a><a name="getactivationfactory"></a>Модуль::GetActivationFactory

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

*Имя _сервера*<br/>
Имя подмножества фабрик класса в текущем модуле. Укажите имя сервера, используемое в макросе `nullptr` [ActivatableWithFactoryEx,](activatableclass-macros.md) или укажите, чтобы получить имя сервера по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, возвращаемое GetActivationFactory.

## <a name="modulegetclassobject"></a><a name="getclassobject"></a>Модуль::GetClassObject

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

*clsid*<br/>
Идентификатор класса.

*riid*<br/>
Запрошенный идентификатор интерфейса.

*Ppv*<br/>
Указатель на возвращаемый объект.

*Имя _сервера*<br/>
Имя сервера, указанное в макросе `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx` или `ActivatableClass`; в противном случае — значение `nullptr` для получения имени сервера по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Используйте этот метод только для COM, а не для Windows Runtime. Этот метод предоставляет `IClassFactory` только методы.

## <a name="modulegetmodule"></a><a name="getmodule"></a>Модуль::GetModule

Создает экземпляр модуля.

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на модуль.

## <a name="modulegetobjectcount"></a><a name="getobjectcount"></a>Модуль::GetObjectCount

Извлекает количество объектов, управляемых этим модулем.

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее количество объектов, управляемых этим модулем.

## <a name="moduleincrementobjectcount"></a><a name="incrementobjectcount"></a>Модуль::ИнкрементныйОбъективКтом

Приравливки количество объектов, отслеживаемых модулем.

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>Возвращаемое значение

Подсчет перед операцией приращения.

## <a name="modulemodule"></a><a name="module"></a>Модуль::Модуль

Инициализирует новый экземпляр класса `Module`.

```cpp
Module();
```

### <a name="remarks"></a>Remarks

Этот конструктор является защищенным и не может быть вызван ключевым словом `new`. Вместо этого позвоните либо [в модуль::GetModule](#getmodule) или [Модуль::Создать](#create).

## <a name="moduleobjectcount_"></a><a name="objectcount"></a>Модуль::objectCount_

Отслеживает, сколько классов было создано с функцией [Make.](make-function.md)

```cpp
volatile long objectCount_;
```

## <a name="moduleregistercomobject"></a><a name="registercomobject"></a>Модуль::RegisterCOMObject

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

*Имя _сервера*<br/>
Полное имя сервера.

*clsids*<br/>
Массив регистрируемых идентификаторов CLSID.

*Заводов*<br/>
Массив интерфейсов IUnknown объектов класса, чья доступность публикуется.

*Печенье*<br/>
После завершения операции представляет массив указателей на значения, которые определяют зарегистрированные объекты класса. Эти значения в дальнейшем используются для отмены регистрации.

*count*<br/>
Количество идентификаторов CLSID, которые необходимо зарегистрировать.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT (например, CO_E_OBJISREG), указывающее причину неудачного завершения операции.

### <a name="remarks"></a>Remarks

COM-объекты зарегистрированы с помощью перечислителя CLSCTX_LOCAL_SERVER перечисления CLSCTX.

Тип соединения с зарегистрированными объектами определяется комбинацией текущего параметра шаблона *comflag* и REGCLS_SUSPENDED перечисления в перечислении REGCLS.

## <a name="moduleregisterobjects"></a><a name="registerobjects"></a>Модуль:РегистрацияОбъекты

Регистрирует объекты COM или Windows Runtime, чтобы другие приложения могли подключиться к ним.

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Параметры

*Модуль*<br/>
Массив объектов COM или Windows Runtime.

*Имя _сервера*<br/>
Имя сервера, который создал объекты.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="moduleregisterwinrtobject"></a><a name="registerwinrtobject"></a>Модуль::RegisterWinRTObject

Регистрирует один или несколько объектов Windows Runtime, чтобы другие приложения могли подключиться к ним.

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>Параметры

*Имя _сервера*<br/>
Имя, которое определяет подмножество объектов, затронутых этой операцией.

*активироватьКлассныеи*<br/>
Массив активируемых идентификаторов CLSID для регистрации.

*Cookie*<br/>
Значение, которое идентифицирует зарегистрированные объекты класса. Это значение в дальнейшем используется для отмены регистрации.

*count*<br/>
Количество объектов, которое необходимо зарегистрировать.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT (например, CO_E_OBJISREG), указывающее причину неудачного завершения операции.

## <a name="modulereleasenotifier_"></a><a name="releasenotifier"></a>Модуль::releaseNotifier_

Удерживает указатель `ReleaseNotifier` на объект.

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="moduleterminate"></a><a name="terminate"></a>Модуль::Прекращение

Приводит к завершению работы всех экземпляров фабрик, созданных модулем.

```cpp
void Terminate();
```

### <a name="remarks"></a>Remarks

Освобождает фабрики в кэше.

## <a name="moduleunregistercomobject"></a><a name="unregistercomobject"></a>Модуль::UnregisterCOMObject

Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>Параметры

*Имя _сервера*<br/>
(Не используется)

*Печенье*<br/>
Массив указателей на значения, которые идентифицируют объекты класса для отмены регистрации. Массив был создан методом [RegisterCOMObject.](#registercomobject)

*count*<br/>
Количество классов для отмены регистрации.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="moduleunregisterobjects"></a><a name="unregisterobjects"></a>Модуль::Нерегистраемыеобъекты

Отменяет регистрацию объектов в указанном модуле. Таким образом другие приложения не смогут подключиться к ним.

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Параметры

*Модуль*<br/>
Указатель на модуль.

*Имя _сервера*<br/>
Представляет имя, которое определяет подмножество объектов, затронутых этой операцией.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.

## <a name="moduleunregisterwinrtobject"></a><a name="unregisterwinrtobject"></a>Модуль::UnregisterWinRTObject

Отменить регистрацию одного или нескольких объектов Windows Runtime, чтобы другие приложения не могли подключиться к ним.

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>Параметры

*Cookie*<br/>
Указатель на значение, определяющее объект класса, регистрация которого должна быть отменена.
