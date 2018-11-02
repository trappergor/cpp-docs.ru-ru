---
title: ChainInterfaces - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
- implements/Microsoft::WRL::ChainInterfaces::CastToUnknown
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
- implements/Microsoft::WRL::ChainInterfaces::IidCount
- implements/Microsoft::WRL::ChainInterfaces::Verify
helpviewer_keywords:
- Microsoft::WRL::ChainInterfaces structure
- Microsoft::WRL::ChainInterfaces::CanCastTo method
- Microsoft::WRL::ChainInterfaces::CastToUnknown method
- Microsoft::WRL::ChainInterfaces::FillArrayWithIid method
- Microsoft::WRL::ChainInterfaces::IidCount constant
- Microsoft::WRL::ChainInterfaces::Verify method
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
ms.openlocfilehash: 87967f733cbb6ae2db999232c57751521d77fdc7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552702"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces - структура

Указывает функции проверки и инициализации, которые могут применяться к набору идентификаторов интерфейсов.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename I0,
    typename I1,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct ChainInterfaces : I0;

template <
    typename DerivedType,
    typename BaseType,
    bool hasImplements,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8,
    typename I9
>
struct ChainInterfaces<
    MixIn<
        DerivedType,
        BaseType,
        hasImplements
    >, I1, I2, I3, I4, I5, I6, I7, I8, I9
>;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
(Обязательно) Идентификатор интерфейса 0.

*I1*<br/>
(Обязательно) Идентификатор интерфейса 1.

*I2*<br/>
(Необязательно) Идентификатор интерфейса 2.

*I3*<br/>
(Необязательно) Идентификатор интерфейса 3.

*I4*<br/>
(Необязательно) Идентификатор интерфейса. 4.

*I5*<br/>
(Необязательно) Идентификатор интерфейса 5.

*I6*<br/>
(Необязательно) Идентификатор интерфейса 6.

*I7*<br/>
(Необязательно) Идентификатор интерфейса 7.

*I8*<br/>
(Необязательно) Идентификатор интерфейса 8.

*I9*<br/>
(Необязательно) Идентификатор интерфейса 9.

*DerivedType*<br/>
Производный тип.

*BaseType*<br/>
Базовый тип производного типа.

*hasImplements*<br/>
Логическое значение, если **true**, означает, что нельзя использовать [Примеси](../windows/mixin-structure.md) структуру с классом, который является производным от [реализует](../windows/implements-structure.md) структура.

## <a name="members"></a>Участники

### <a name="protected-methods"></a>Защищенные методы

Имя                                                   | Описание
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ChainInterfaces::CanCastTo](#cancastto)               | Указывает ли идентификатор указанный интерфейс может быть приведен к каждому из специализаций, определяется `ChainInterface` параметров шаблона.
[ChainInterfaces::CastToUnknown](#casttounknown)       | Приведение указателя интерфейса типа, определенного с *I0* параметр шаблона в указатель на `IUnknown`.
[ChainInterfaces::FillArrayWithIid](#fillarraywithiid) | Идентификатор интерфейса определяется хранилищ *I0* параметр шаблона в указанном расположении в указанном массиве идентификаторов интерфейсов.
[ChainInterfaces::Verify](#verify)                     | Проверяет, что каждому интерфейсу, определяемая параметрами шаблона *I0* через *I9* наследует от `IUnknown` и/или `IInspectable`и что *I0* наследует от *I1* через *I9*.

### <a name="protected-constants"></a>Защищенные константы

name                                   | Описание
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[ChainInterfaces::IidCount](#iidcount) | Общее количество содержащихся в интерфейсах, указанные параметрами шаблона идентификаторы интерфейсов *I0* через *I9*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`I0`

`ChainInterfaces`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="cancastto"></a>ChainInterfaces::CanCastTo

Указывает ли идентификатор указанный интерфейс может быть приведен к каждому из специализаций, определяемая параметрами шаблона не по умолчанию.

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ppv*<br/>
Указатель на последний идентификатор интерфейса, который был приведен успешно.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если все операции приведения выполнена успешно; в противном случае **false**.

## <a name="casttounknown"></a>ChainInterfaces::CastToUnknown

Приведение указателя интерфейса типа, определенного с *I0* параметр шаблона в указатель на `IUnknown`.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IUnknown`.

## <a name="fillarraywithiid"></a>ChainInterfaces::FillArrayWithIid

Идентификатор интерфейса определяется хранилищ *I0* параметр шаблона в указанном расположении в указанном массиве идентификаторов интерфейсов.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Указатель на значение индекса в *идентификаторы IID* массива.

*идентификаторы IID*<br/>
Массив идентификаторов интерфейсов.

## <a name="iidcount"></a>ChainInterfaces::IidCount

Общее количество содержащихся в интерфейсах, указанные параметрами шаблона идентификаторы интерфейсов *I0* через *I9*.

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>Возвращаемое значение

Общее число идентификаторов интерфейса.

### <a name="remarks"></a>Примечания

Параметры шаблона *I0* и *I1* являются обязательными и параметры *I2* через *I9* являются необязательными. Количество каждого интерфейса IID обычно равно 1.

## <a name="verify"></a>ChainInterfaces::Verify

Проверяет, что каждому интерфейсу, определяемая параметрами шаблона *I0* через *I9* наследует от `IUnknown` и/или `IInspectable`и что *I0* наследует от *I1* через *I9*.

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>Примечания

Если операция проверки завершается ошибкой, `static_assert` выдает сообщение об ошибке с описанием причины.

Параметры шаблона *I0* и *I1* являются обязательными и параметры *I2* через *I9* являются необязательными.
