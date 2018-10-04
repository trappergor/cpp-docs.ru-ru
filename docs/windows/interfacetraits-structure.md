---
title: Interfacetraits-структура | Документация Майкрософт
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
- implements/Microsoft::WRL::Details::InterfaceTraits::IidCount
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::InterfaceTraits structure
- Microsoft::WRL::Details::InterfaceTraits::CanCastTo method
- Microsoft::WRL::Details::InterfaceTraits::CastToBase method
- Microsoft::WRL::Details::InterfaceTraits::CastToUnknown method
- Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid method
- Microsoft::WRL::Details::InterfaceTraits::IidCount constant
- Microsoft::WRL::Details::InterfaceTraits::Verify method
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e184d9e5b99cd59d4dde63b06cbe259d328a0e4e
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234688"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<
   typename I0
>
struct __declspec(novtable) InterfaceTraits;
template<typename CloakedType>
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;

template<>
struct __declspec(novtable) InterfaceTraits<Nil>;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
Имя интерфейса.

*CloakedType*<br/>
Для `RuntimeClass`, `Implements` и `ChainInterfaces`, интерфейс, который не будет в списке поддерживаемых идентификаторы интерфейсов.

## <a name="remarks"></a>Примечания

Реализует общие характеристики интерфейса.

Второй шаблон является специализацией замаскированных интерфейсов. Третий шаблон является специализацией Nil параметров.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

name   | Описание
------ | ------------------------------------------
`Base` | Синоним для *I0* параметр шаблона.

### <a name="public-methods"></a>Открытые методы

Имя                                                   | Описание
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[InterfaceTraits::CanCastTo](#cancastto)               | Указывает ли заданный указатель может быть приведен к указателю на `Base`.
[InterfaceTraits::CastToBase](#casttobase)             | Приводит определенный указатель к указателю на `Base`.
[InterfaceTraits::CastToUnknown](#casttounknown)       | Приводит определенный указатель к указателю на `IUnknown`.
[InterfaceTraits::FillArrayWithIid](#fillarraywithiid) | Назначает идентификатор интерфейса `Base` к элементу массива, указанного аргументом индекса.
[InterfaceTraits::Verify](#verify)                     | Проверяет, что `Base` должным образом является производным.

### <a name="public-constants"></a>Открытые константы

name                                   | Описание
-------------------------------------- | ---------------------------------------------------------------------------------------
[InterfaceTraits::IidCount](#iidcount) | Содержит номер интерфейса идентификаторов, связанных с текущим `InterfaceTraits` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InterfaceTraits`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="cancastto"></a>InterfaceTraits::CanCastTo

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*ptr*<br/>
Имя указателя на тип.

*riid*<br/>
Идентификатор интерфейса `Base`.

*ppv*<br/>
Если операция выполнена успешно, *ppv* указывает на интерфейсе, указанном свойством `Base`. В противном случае *ppv* присваивается `nullptr`.

### <a name="return-value"></a>Возвращаемое значение

`true` При успешном выполнении этой операции и *ptr* приведен к указателю на `Base`; в противном случае `false` .

### <a name="remarks"></a>Примечания

Указывает ли заданный указатель может быть приведен к указателю на `Base`.

Дополнительные сведения о `Base`, см. в разделе [общедоступные определения типов](#public-typedefs) раздел.

## <a name="casttobase"></a>InterfaceTraits::CastToBase

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип параметра *ptr*.

*ptr*<br/>
Указатель на тип *T*.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `Base`.

### <a name="remarks"></a>Примечания

Приводит определенный указатель к указателю на `Base`.

Дополнительные сведения о `Base`, см. в разделе [общедоступные определения типов](#public-typedefs) раздел.

## <a name="casttounknown"></a>InterfaceTraits::CastToUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип параметра *ptr*.

*ptr*<br/>
Указатель на тип *T*.

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IUnknown, из которого `Base` является производным.

### <a name="remarks"></a>Примечания

Приводит определенный указатель к указателю на `IUnknown`.

Дополнительные сведения о `Base`, см. в разделе [общедоступные определения типов](#public-typedefs) раздел.

## <a name="fillarraywithiid"></a>InterfaceTraits::FillArrayWithIid

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Указатель на поле, содержащее значение отсчитываемый от нуля индекс.

*идентификаторы IID*<br/>
Массив идентификаторов интерфейсов.

### <a name="remarks"></a>Примечания

Назначает идентификатор интерфейса `Base` к элементу массива, указанного аргументом индекса.

В отличие от имени этого API только один массив изменяется; не весь массив.

Дополнительные сведения о `Base`, см. в разделе [общедоступные определения типов](#public-typedefs) раздел.

## <a name="iidcount"></a>InterfaceTraits::IidCount

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>Примечания

Содержит номер интерфейса идентификаторов, связанных с текущим `InterfaceTraits` объекта.

## <a name="verify"></a>InterfaceTraits::Verify

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>Примечания

Проверяет, что `Base` должным образом является производным.

Дополнительные сведения о `Base`, см. в разделе [общедоступные определения типов](#public-typedefs) раздел.
