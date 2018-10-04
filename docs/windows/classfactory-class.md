---
title: Класс ClassFactory | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
- module/Microsoft::WRL::ClassFactory::AddRef
- module/Microsoft::WRL::ClassFactory::ClassFactory
- module/Microsoft::WRL::ClassFactory::LockServer
- module/Microsoft::WRL::ClassFactory::QueryInterface
- module/Microsoft::WRL::ClassFactory::Release
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::ClassFactory class
- Microsoft::WRL::ClassFactory::AddRef method
- Microsoft::WRL::ClassFactory::ClassFactory, constructor
- Microsoft::WRL::ClassFactory::LockServer method
- Microsoft::WRL::ClassFactory::QueryInterface method
- Microsoft::WRL::ClassFactory::Release method
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e3639bb9d6ca88862b3a2fb4367fc429a665287
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788673"
---
# <a name="classfactory-class"></a>ClassFactory - класс

Реализует базовую функциональность интерфейса `IClassFactory`.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ClassFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IClassFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<ClassicCom | InhibitWeakReference>,
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

Использовать `ClassFactory` для обеспечения реализации пользовательской фабрики.

Следующий шаблон программирования демонстрирует использование [реализует](../windows/implements-structure.md) структура для указания более трех интерфейсов на фабрику класса.

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                        | Описание
------------------------------------------- | -----------
[ClassFactory::ClassFactory](#classfactory) |

### <a name="public-methods"></a>Открытые методы

Имя                                            | Описание
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[ClassFactory::AddRef](#addref)                 | Увеличивает счетчик ссылок для текущего `ClassFactory` объекта.
[ClassFactory::LockServer](#lockserver)         | Увеличивает или уменьшает число базовых объектов, отслеживаемых текущим `ClassFactory` объекта.
[ClassFactory::QueryInterface](#queryinterface) | Извлекает указатель на интерфейс, заданный параметром.
[ClassFactory::Release](#release)               | Уменьшает счетчик ссылок для текущего `ClassFactory` объекта.

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

`ClassFactory`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="addref"></a>ClassFactory::AddRef

Увеличивает счетчик ссылок для текущего `ClassFactory` объекта.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="classfactory"></a>ClassFactory::ClassFactory

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="lockserver"></a>ClassFactory::LockServer

Увеличивает или уменьшает число базовых объектов, отслеживаемых текущим `ClassFactory` объекта.

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>Параметры

*fLock*<br/>
Значение `true` для увеличения числа отслеживаемых объектов. Значение `false` для уменьшения числа отслеживаемых объектов.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение E_FAIL.

### <a name="remarks"></a>Примечания

`ClassFactory` следит за объектов в базовом экземпляре класса [модуль](../windows/module-class.md) класса.

## <a name="queryinterface"></a>ClassFactory::QueryInterface

Извлекает указатель на интерфейс, заданный параметром.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ppvObject*<br/>
После завершения операции, указатель на интерфейс, заданный параметром *riid*.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="release"></a>ClassFactory::Release

Уменьшает счетчик ссылок для текущего `ClassFactory` объекта.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.
