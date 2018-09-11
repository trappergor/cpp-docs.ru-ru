---
title: Реализует структуру | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements
dev_langs:
- C++
helpviewer_keywords:
- Implements structure
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 417f384b54833786c68fe2b13dc9e7e53b1bc975
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603292"
---
# <a name="implements-structure"></a>Implements - структура

Реализует `QueryInterface` и `GetIid` для указанных интерфейсов.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename I0,
   typename I1 = Details::Nil,
   typename I2 = Details::Nil,
   typename I3 = Details::Nil,
   typename I4 = Details::Nil,
   typename I5 = Details::Nil,
   typename I6 = Details::Nil,
   typename I7 = Details::Nil,
   typename I8 = Details::Nil,
   typename I9 = Details::Nil
>
struct __declspec(novtable) Implements : Details::ImplementsHelper<RuntimeClassFlags<WinRt>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT>, Details::ImplementsBase;
template <
   int flags,
   typename I0,
   typename I1,
   typename I2,
   typename I3,
   typename I4,
   typename I5,
   typename I6,
   typename I7,
   typename I8
>
struct __declspec(novtable) Implements<RuntimeClassFlags<flags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : Details::ImplementsHelper<RuntimeClassFlags<flags>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT>, Details::ImplementsBase;
```

### <a name="parameters"></a>Параметры

*I0*  
Идентификатор нулевого интерфейса. (Обязательный)

*I1*  
Идентификатор первого интерфейса. (Необязательный параметр).

*I2*  
Идентификатор второго интерфейса. (Необязательный параметр).

*I3*  
Идентификатор третьего интерфейса. (Необязательный параметр).

*I4*  
Идентификатор четвертого интерфейса. (Необязательный параметр).

*I5*  
Идентификатор пятого интерфейса. (Необязательный параметр).

*I6*  
Идентификатор шестого интерфейса. (Необязательный параметр).

*I7*  
Идентификатор седьмого интерфейса. (Необязательный параметр).

*I8*  
Идентификатор восьмого интерфейса. (Необязательный параметр).

*I9*  
Идентификатор девятого интерфейса. (Необязательный параметр).

*flags*  
Флаги конфигурации для класса. Один или несколько [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) перечисления, которые указаны в [RuntimeClassFlags](../windows/runtimeclassflags-structure.md) структуры.

## <a name="remarks"></a>Примечания

Является производным от списка указанных интерфейсов и реализует вспомогательные шаблоны для `QueryInterface` и `GetIid`.

Каждый *I0* через *I9* параметр интерфейса должен быть производным от `IUnknown`, `IInspectable`, или [ChainInterfaces](../windows/chaininterfaces-structure.md) шаблона. *Флаги* параметр определяет, создается ли поддержка для `IUnknown` или `IInspectable`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`ClassFlags`|Синоним для `RuntimeClassFlags<WinRt>`.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание:|
|----------|-----------------|
|[Метод Implements::CanCastTo](../windows/implements-cancastto-method.md)|Возвращает указатель на указанный интерфейс.|
|[Метод Implements::CastToUnknown](../windows/implements-casttounknown-method.md)|Возвращает указатель на базовый `IUnknown` интерфейс.|
|[Метод Implements::FillArrayWithIid](../windows/implements-fillarraywithiid-method.md)|Вставляет идентификатор интерфейса, заданный текущим параметром шаблона признаками в указанный элемент массива.|

### <a name="protected-constants"></a>Защищенные константы

|name|Описание:|
|----------|-----------------|
|[Константа Implements::IidCount](../windows/implements-iidcount-constant.md)|Содержит число идентификаторов реализованного интерфейса.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`I0`

`ChainInterfaces`

`I0`

`ImplementsBase`

`ImplementsHelper`

`Implements`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)