---
title: InterfaceTraits - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
- implements/Microsoft::WRL::Details::InterfaceTraits::IidCount
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::InterfaceTraits structure
- Microsoft::WRL::Details::InterfaceTraits::CanCastTo method
- Microsoft::WRL::Details::InterfaceTraits::CastToBase method
- Microsoft::WRL::Details::InterfaceTraits::CastToUnknown method
- Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid method
- Microsoft::WRL::Details::InterfaceTraits::IidCount constant
- Microsoft::WRL::Details::InterfaceTraits::Verify method
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
ms.openlocfilehash: 17f743a38af3ddc600a55e38905d19868d076a22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371373"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename I0>
struct __declspec(novtable) InterfaceTraits;

template<typename CloakedType>
struct __declspec(novtable) InterfaceTraits<
    CloakedIid<CloakedType>
>;

template<>
struct __declspec(novtable) InterfaceTraits<Nil>;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
Название интерфейса.

*ЗамаскированныйТип*<br/>
Для `RuntimeClass` `Implements` , `ChainInterfaces`и , интерфейс, который не будет в списке поддерживаемых идентипов интерфейса.

## <a name="remarks"></a>Remarks

Реализует общие характеристики интерфейса.

Второй шаблон представляет собой специализацию для скрытых интерфейсов. Третий шаблон является специализацией для параметров Nil.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a><a name="public-typedefs"></a>Публичные Типдефы

Имя   | Описание
------ | ------------------------------------------
`Base` | Синоним параметра *шаблона I0.*

### <a name="public-methods"></a>Открытые методы

Имя                                                   | Описание
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[Интерфейсные приложения::CancastTo](#cancastto)               | Указывает, может ли указанный указатель быть `Base`отлит на указатель.
[Интерфейсты::CastToBase](#casttobase)             | Приводит определенный указатель к указателю на `Base`.
[Интерфейсы::CastToUnknown](#casttounknown)       | Приводит определенный указатель к указателю на `IUnknown`.
[InterfaceTraits::FillArrayWithIid](#fillarraywithiid) | Присваивает `Base` идентификатор интерфейса элементу массива, указанному аргументом индекса.
[ИнтерфейсТрэйты::Проверить](#verify)                     | Проверяет, что `Base` правильно производные.

### <a name="public-constants"></a>Открытые константы

Имя                                   | Описание
-------------------------------------- | ---------------------------------------------------------------------------------------
[ИнтерфейсТрэйты::IidCount](#iidcount) | Сохраняет сятное количество идотов интерфейса, связанных с текущим `InterfaceTraits` объектом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InterfaceTraits`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="interfacetraitscancastto"></a><a name="cancastto"></a>Интерфейсные приложения::CancastTo

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*Ptr*<br/>
Имя указателя на тип.

*riid*<br/>
Идентификатор интерфейса `Base`.

*Ppv*<br/>
Если эта операция прошла успешно, *ppv* `Base`указывает на указанный интерфейс . В противном случае, `nullptr` *ppv* установлен на .

### <a name="return-value"></a>Возвращаемое значение

**верно,** если эта операция является успешной и `Base` *ptr* отбрасывается на указатель на ; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Указывает, может ли указанный указатель быть `Base`отлит на указатель.

Для получения `Base`дополнительной информации о разделе [Public Typedefs.](#public-typedefs)

## <a name="interfacetraitscasttobase"></a><a name="casttobase"></a>Интерфейсты::CastToBase

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип параметра *ptr*.

*Ptr*<br/>
Указатель на тип *T*.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `Base`.

### <a name="remarks"></a>Remarks

Приводит определенный указатель к указателю на `Base`.

Для получения `Base`дополнительной информации о разделе [Public Typedefs.](#public-typedefs)

## <a name="interfacetraitscasttounknown"></a><a name="casttounknown"></a>Интерфейсы::CastToUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип параметра *ptr*.

*Ptr*<br/>
Указатель на *визу*Т .

### <a name="return-value"></a>Возвращаемое значение

Указатель на IUnknown, `Base` из которого происходит.

### <a name="remarks"></a>Remarks

Приводит определенный указатель к указателю на `IUnknown`.

Для получения `Base`дополнительной информации о разделе [Public Typedefs.](#public-typedefs)

## <a name="interfacetraitsfillarraywithiid"></a><a name="fillarraywithiid"></a>InterfaceTraits::FillArrayWithIid

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Указатель на поле, содержащее значение индекса с нулевым уровнем.

*iids*<br/>
Массив идов интерфейса.

### <a name="remarks"></a>Remarks

Присваивает `Base` идентификатор интерфейса элементу массива, указанному аргументом индекса.

В отличие от названия этого API, изменяется только один элемент массива; не весь массив.

Для получения `Base`дополнительной информации о разделе [Public Typedefs.](#public-typedefs)

## <a name="interfacetraitsiidcount"></a><a name="iidcount"></a>ИнтерфейсТрэйты::IidCount

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>Remarks

Сохраняет сятное количество идотов интерфейса, связанных с текущим `InterfaceTraits` объектом.

## <a name="interfacetraitsverify"></a><a name="verify"></a>ИнтерфейсТрэйты::Проверить

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>Remarks

Проверяет, что `Base` правильно производные.

Для получения `Base`дополнительной информации о разделе [Public Typedefs.](#public-typedefs)
