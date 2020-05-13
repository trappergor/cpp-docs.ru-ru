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
ms.openlocfilehash: dd1af3fb5c1079a40d8248dc71ae4972537aa856
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372655"
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
(Обязательно) Интерфейс ID 1.

*I2*<br/>
(Необязательно) Интерфейс ID 2.

*I3*<br/>
(Необязательно) Интерфейс ID 3.

*I4*<br/>
(Необязательно) Интерфейс ID 4.

*I5*<br/>
(Необязательно) Интерфейс ID 5.

*I6*<br/>
(Необязательно) Интерфейс ID 6.

*I7*<br/>
(Необязательно) Интерфейс ID 7.

*I8*<br/>
(Необязательно) Интерфейс ID 8.

*I9*<br/>
(Необязательно) Интерфейс ID 9.

*Производныйтип*<br/>
Производный тип.

*BaseType*<br/>
Базовый тип производного типа.

*hasImplements*<br/>
Boolean значение, что если **верно,** означает, что вы не можете использовать [MixIn](mixin-structure.md) структуры с классом, который не вытекает из [перфекций лепнины.](implements-structure.md)

## <a name="members"></a>Участники

### <a name="protected-methods"></a>Защищенные методы

Имя                                                   | Описание
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ЦепьИнтерфейсы::CanCastTo](#cancastto)               | Указывает, можно ли отлить указанный идентификатор `ChainInterface` интерфейса к каждой из специализаций, определенных параметрами шаблона.
[ЦепьИнтерфейсы::CastToUnknown](#casttounknown)       | Отбрасывает указатель интерфейса типа, определенного параметром шаблона `IUnknown` *I0,* указателю на .
[ЦепьИнтерфейсы::FillArrayWithIid](#fillarraywithiid) | Хранит идентификатор интерфейса, определяемый параметром шаблона *I0,* в определенном месте в определенном массиве идентификаторов интерфейса.
[ЦепьИнтерфейсы::Проверить](#verify)                     | Проверяет, что каждый интерфейс, определяемый параметрами `IInspectable`шаблона *I0* через *I9,* наследует от `IUnknown` и/или, и что *I0* наследует от *I1* через *I9*.

### <a name="protected-constants"></a>Защищенные константы

Имя                                   | Описание
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[ЦепьИнтерфейсы::IidCount](#iidcount) | Общее количество идотов интерфейса, содержащихся в интерфейсах, указанных параметрами *шаблонов I0* через *I9*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`I0`

`ChainInterfaces`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="chaininterfacescancastto"></a><a name="cancastto"></a>ЦепьИнтерфейсы::CanCastTo

Указывает, может ли указанный идентификатор интерфейса быть отлит в каждую из специализаций, определенных параметрами шаблона без умолчанию.

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*Ppv*<br/>
Указатель на последний идентификатор интерфейса, который был отлит успешно.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если все литые операции удалось; в противном случае, **ложные**.

## <a name="chaininterfacescasttounknown"></a><a name="casttounknown"></a>ЦепьИнтерфейсы::CastToUnknown

Отбрасывает указатель интерфейса типа, определенного параметром шаблона `IUnknown` *I0,* указателю на .

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `IUnknown`.

## <a name="chaininterfacesfillarraywithiid"></a><a name="fillarraywithiid"></a>ЦепьИнтерфейсы::FillArrayWithIid

Хранит идентификатор интерфейса, определяемый параметром шаблона *I0,* в определенном месте в определенном массиве идентификаторов интерфейса.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Указатель на значение индекса в массив *iids.*

*iids*<br/>
Массив идов интерфейса.

## <a name="chaininterfacesiidcount"></a><a name="iidcount"></a>ЦепьИнтерфейсы::IidCount

Общее количество идотов интерфейса, содержащихся в интерфейсах, указанных параметрами *шаблонов I0* через *I9*.

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>Возвращаемое значение

Общее количество идотов интерфейса.

### <a name="remarks"></a>Remarks

Параметры шаблона *I0* и *I1* обязательны, а параметры *I2* через *I9* неявляются. Количество IID каждого интерфейса обычно составляет 1.

## <a name="chaininterfacesverify"></a><a name="verify"></a>ЦепьИнтерфейсы::Проверить

Проверяет, что каждый интерфейс, определяемый параметрами `IInspectable`шаблона *I0* через *I9,* наследует от `IUnknown` и/или, и что *I0* наследует от *I1* через *I9*.

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>Remarks

Если операция проверки завершается ошибкой, `static_assert` выдает сообщение об ошибке с описанием причины.

Параметры шаблона *I0* и *I1* обязательны, а параметры *I2* через *I9* неявляются.
