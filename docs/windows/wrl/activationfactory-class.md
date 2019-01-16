---
title: ActivationFactory - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::AddRef
- module/Microsoft::WRL::ActivationFactory::GetIids
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
- module/Microsoft::WRL::ActivationFactory::QueryInterface
- module/Microsoft::WRL::ActivationFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ActivationFactory class
- Microsoft::WRL::ActivationFactory::ActivationFactory, constructor
- Microsoft::WRL::ActivationFactory::AddRef method
- Microsoft::WRL::ActivationFactory::GetIids method
- Microsoft::WRL::ActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::ActivationFactory::GetTrustLevel method
- Microsoft::WRL::ActivationFactory::QueryInterface method
- Microsoft::WRL::ActivationFactory::Release method
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
ms.openlocfilehash: 8e5132f4a8711f6420cd9b52751550a96d10d8fc
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336592"
---
# <a name="activationfactory-class"></a>ActivationFactory - класс

Позволяет одному или нескольким классам быть активированными средой выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ActivationFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IActivationFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<WinRt | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
Интерфейс признаками.

*I1*<br/>
Первый интерфейс.

*I2*<br/>
Второй интерфейс.

## <a name="remarks"></a>Примечания

`ActivationFactory` Предоставляет методы регистрации и базовые функциональные возможности для `IActivationFactory` интерфейс. `ActivationFactory` также предоставляет возможность реализации пользовательской фабрики.

В следующем фрагменте кода символически описывается использование ActivationFactory.

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

В следующем фрагменте кода показано, как использовать [реализует](implements-structure.md) структуры, чтобы указать более чем на три ИД интерфейса.

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                       | Описание:
---------------------------------------------------------- | ------------------------------------------
[ActivationFactory::ActivationFactory](#activationfactory) | Инициализирует `ActivationFactory` класса.

### <a name="public-methods"></a>Открытые методы

Имя                                                           | Описание:
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[ActivationFactory::AddRef](#addref)                           | Увеличивает счетчик ссылок текущего `ActivationFactory` объекта.
[ActivationFactory::GetIids](#getiids)                         | Извлекает массив идентификаторов реализованного интерфейса.
[ActivationFactory::GetRuntimeClassName](#getruntimeclassname) | Получает имя класса среды выполнения объекта, который текущего `ActivationFactory` создает экземпляр.
[ActivationFactory::GetTrustLevel](#gettrustlevel)             | Получает уровень доверия объект, текущий `ActivationFactory` создает экземпляр.
[ActivationFactory::QueryInterface](#queryinterface)           | Извлекает указатель на указанный интерфейс.
[ActivationFactory::Release](#release)                         | Уменьшает счетчик ссылок текущего `ActivationFactory` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="activationfactory"></a>ActivationFactory::ActivationFactory

Инициализирует `ActivationFactory` класса.

```cpp
ActivationFactory();
```

## <a name="addref"></a>ActivationFactory::AddRef

Увеличивает счетчик ссылок текущего `ActivationFactory` объекта.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="getiids"></a>ActivationFactory::GetIids

Извлекает массив идентификаторов реализованного интерфейса.

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Параметры

*iidCount*<br/>
После завершения операции, число идентификаторов интерфейса в *идентификаторы IID* массива.

*идентификаторы IID*<br/>
После завершения операции представляет массив идентификаторов реализованного интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. E_OUTOFMEMORY является возможной ошибкой HRESULT.

## <a name="getruntimeclassname"></a>ActivationFactory::GetRuntimeClassName

Получает имя класса среды выполнения объекта, который текущего `ActivationFactory` создает экземпляр.

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>Параметры

*runtimeName*<br/>
После завершения операции, дескриптор строка, содержащая имя класса среды выполнения объекта, текущий `ActivationFactory` создает экземпляр.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="gettrustlevel"></a>ActivationFactory::GetTrustLevel

Получает уровень доверия объект, текущий `ActivationFactory` создает экземпляр.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>Параметры

*trustLvl*<br/>
После завершения этой операции, уровень доверия среды выполнения класс, который `ActivationFactory` создает экземпляр.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае выдается ошибка утверждения и *trustLvl* присваивается `FullTrust`.

## <a name="queryinterface"></a>ActivationFactory::QueryInterface

Извлекает указатель на указанный интерфейс.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ppvObject*<br/>
Когда эта операция будет завершена, указатель на интерфейс, заданный параметром *riid*.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="release"></a>ActivationFactory::Release

Уменьшает счетчик ссылок текущего `ActivationFactory` объекта.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.
