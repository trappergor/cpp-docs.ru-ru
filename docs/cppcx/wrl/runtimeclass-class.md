---
title: Класс RuntimeClass
ms.date: 09/11/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::AddRef
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
- implements/Microsoft::WRL::RuntimeClass::GetIids
- implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
- implements/Microsoft::WRL::RuntimeClass::QueryInterface
- implements/Microsoft::WRL::RuntimeClass::Release
- implements/Microsoft::WRL::RuntimeClass::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::~RuntimeClass
helpviewer_keywords:
- Microsoft::WRL::RuntimeClass class
- Microsoft::WRL::RuntimeClass::AddRef method
- Microsoft::WRL::RuntimeClass::DecrementReference method
- Microsoft::WRL::RuntimeClass::GetIids method
- Microsoft::WRL::RuntimeClass::GetRuntimeClassName method
- Microsoft::WRL::RuntimeClass::GetTrustLevel method
- Microsoft::WRL::RuntimeClass::GetWeakReference method
- Microsoft::WRL::RuntimeClass::InternalAddRef method
- Microsoft::WRL::RuntimeClass::QueryInterface method
- Microsoft::WRL::RuntimeClass::Release method
- Microsoft::WRL::RuntimeClass::RuntimeClass, constructor
- Microsoft::WRL::RuntimeClass::~RuntimeClass, destructor
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
ms.openlocfilehash: d45fe7c6d794f216da93ffbd95dbb7058d3336f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403195"
---
# <a name="runtimeclass-class"></a>Класс RuntimeClass

Представляет класс WinRT или COM, который наследует указанных интерфейсов и предоставляет указанной среды выполнения Windows, классическую COM-модель и поддержку слабых ссылок.

Этот класс предоставляет реализацию шаблона классов WinRT и COM, предоставляющей реализацию `QueryInterface`, `AddRef`, `Release` и т.д., управляет счетчик ссылок модуля и включает поддержку фабрика класса для предоставления Активируемый объекты.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>Параметры

*classFlags*<br/>
Необязательный параметр. Сочетание одного или нескольких [RuntimeClassType](runtimeclasstype-enumeration.md) значений перечисления. `__WRL_CONFIGURATION_LEGACY__` Макрос можно определить таким образом, чтобы изменить значение по умолчанию classFlags для всех классов среды выполнения в проекте. Если определено, экземпляры RuntimeClass, не являются гибкими по умолчанию. Если не определен, RuntimeClass экземпляры являются гибкими по умолчанию. Чтобы избежать неоднозначности всегда указывайте `Microsoft::WRL::FtmBase` в `TInterfaces` или `RuntimeClassType::InhibitFtmBase`. Обратите внимание, если InhibitFtmBase и FtmBase, как использовать объект будет agile.

*TInterfaces*<br/>
Список интерфейсов, реализуемых объектом за пределами `IUnknown`, `IInspectable` или других интерфейсов, которые управляются [RuntimeClassType](runtimeclasstype-enumeration.md). Он также может перечислять других классов, производный от, в частности `Microsoft::WRL::FtmBase` сделать объект гибкой и вызвать его, чтобы реализовать `IMarshal`.

## <a name="members"></a>Участники

`RuntimeClassInitialize`<br/>
Функция, которая инициализирует объект, если `MakeAndInitialize` функция-шаблон используется для создания объекта. Возвращается значение S_OK, если объект успешно инициализирован, или код ошибки COM. Если не удалось инициализировать. Код ошибки COM. распространяется как возвращаемое значение `MakeAndInitialize`. Обратите внимание, что `RuntimeClassInitialize` метод не вызывается, если `Make` функция-шаблон используется для создания объекта.

### <a name="public-constructors"></a>Открытые конструкторы

| name                                               | Описание                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [RuntimeClass::RuntimeClass](#runtimeclass)        | Инициализирует текущий экземпляр `RuntimeClass` класса.   |
| [RuntimeClass:: ~ RuntimeClass](#tilde-runtimeclass) | Деинициализирует текущий экземпляр `RuntimeClass` класса. |

### <a name="public-methods"></a>Открытые методы

| name                                                      | Описание                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [RuntimeClass::AddRef](#addref)                           | Увеличивает счетчик ссылок для текущего `RuntimeClass` объекта.                              |
| [RuntimeClass::DecrementReference](#decrementreference)   | Уменьшает счетчик ссылок для текущего `RuntimeClass` объекта.                              |
| [RuntimeClass::GetIids](#getiids)                         | Возвращает массив, который может содержать идентификаторы, реализуется текущим интерфейсов `RuntimeClass` объекта. |
| [RuntimeClass::GetRuntimeClassName](#getruntimeclassname) | Получает имя класса среды выполнения текущего `RuntimeClass` объекта.                                  |
| [RuntimeClass::GetTrustLevel](#gettrustlevel)             | Получает уровень доверия текущего `RuntimeClass` объекта.                                         |
| [RuntimeClass::GetWeakReference](#getweakreference)       | Получает указатель на объект слабой ссылки для текущего `RuntimeClass` объекта.                 |
| [RuntimeClass::InternalAddRef](#internaladdref)           | Увеличивает счетчик ссылок для текущего `RuntimeClass` объекта.                               |
| [RuntimeClass::QueryInterface](#queryinterface)           | Извлекает указатель на идентификатор указанного интерфейса.                                                 |
| [RuntimeClass::Release](#release)                         | Выполняет операцию освобождения модели COM в текущем `RuntimeClass` объекта.                             |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

Это деталь реализации.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="tilde-runtimeclass"></a>RuntimeClass:: ~ RuntimeClass

Деинициализирует текущий экземпляр `RuntimeClass` класса.

```cpp
virtual ~RuntimeClass();
```

## <a name="addref"></a>RuntimeClass::AddRef

Увеличивает счетчик ссылок для текущего `RuntimeClass` объекта.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="decrementreference"></a>RuntimeClass::DecrementReference

Уменьшает счетчик ссылок для текущего `RuntimeClass` объекта.

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="getiids"></a>RuntimeClass::GetIids

Возвращает массив, который может содержать идентификаторы, реализуется текущим интерфейсов `RuntimeClass` объекта.

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Параметры

*iidCount*<br/>
После завершения операции, общее число элементов в массиве *идентификаторы IID*.

*идентификаторы IID*<br/>
После завершения операции представляет указатель на массив идентификаторов интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение E_OUTOFMEMORY.

## <a name="getruntimeclassname"></a>RuntimeClass::GetRuntimeClassName

Получает имя класса среды выполнения текущего `RuntimeClass` объекта.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Параметры

*runtimeName*<br/>
После завершения операции представляет имя класса среды выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Ошибка assert создается в том случае, если `__WRL_STRICT__` или `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` не определена.

## <a name="gettrustlevel"></a>RuntimeClass::GetTrustLevel

Получает уровень доверия текущего `RuntimeClass` объекта.

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Параметры

*trustLvl*<br/>
После завершения операции, уровень доверия текущего `RuntimeClass` объекта.

### <a name="return-value"></a>Возвращаемое значение

Всегда значение S_OK.

### <a name="remarks"></a>Примечания

Ошибка assert создается в том случае, если `__WRL_STRICT__` или `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` не определена.

## <a name="getweakreference"></a>RuntimeClass::GetWeakReference

Получает указатель на объект слабой ссылки для текущего `RuntimeClass` объекта.

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>Параметры

*weakReference*<br/>
После завершения операции представляет указатель на объект слабой ссылки.

### <a name="return-value"></a>Возвращаемое значение

Всегда значение S_OK.

## <a name="internaladdref"></a>RuntimeClass::InternalAddRef

Увеличивает счетчик ссылок для текущего `RuntimeClass` объекта.

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>Возвращаемое значение

Итоговый счетчик ссылок.

## <a name="queryinterface"></a>RuntimeClass::QueryInterface

Извлекает указатель на идентификатор указанного интерфейса.

```cpp
STDMETHOD(
   QueryInterface
)
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ppvObject*<br/>
После завершения этого opereation указатель интерфейса, заданного параметром *riid* параметра.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="release"></a>RuntimeClass::Release

Выполняет операцию освобождения модели COM в текущем `RuntimeClass` объекта.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Если счетчик ссылок становится равным нулю, `RuntimeClass` объект удаляется.

## <a name="runtimeclass"></a>RuntimeClass::RuntimeClass

Инициализирует текущий экземпляр `RuntimeClass` класса.

```cpp
RuntimeClass();
```
