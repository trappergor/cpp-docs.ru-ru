---
title: Структура ChainInterfaces | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
dev_langs:
- C++
helpviewer_keywords:
- ChainInterfaces structure
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88ddd3dd59000b629f6e72933b1a0b02cc582c89
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409875"
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
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;
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

|Имя|Описание|
|----------|-----------------|
|[Метод ChainInterfaces::CanCastTo](../windows/chaininterfaces-cancastto-method.md)|Указывает ли идентификатор указанный интерфейс может быть приведен к каждому из специализаций, определяется **ChainInterface** параметров шаблона.|
|[Метод ChainInterfaces::CastToUnknown](../windows/chaininterfaces-casttounknown-method.md)|Приведение указателя интерфейса типа, определенного с *I0* параметр шаблона в указатель на `IUnknown`.|
|[Метод ChainInterfaces::FillArrayWithIid](../windows/chaininterfaces-fillarraywithiid-method.md)|Идентификатор интерфейса определяется хранилищ *I0* параметр шаблона в указанном расположении в указанном массиве идентификаторов интерфейсов.|
|[Метод ChainInterfaces::Verify](../windows/chaininterfaces-verify-method.md)|Проверяет, что каждому интерфейсу, определяемая параметрами шаблона *I0* через *I9* наследует от `IUnknown` и/или `IInspectable`и что *I0* наследует от *I1* через *I9*.|

### <a name="protected-constants"></a>Защищенные константы

|name|Описание|
|----------|-----------------|
|[Константа ChainInterfaces::IidCount](../windows/chaininterfaces-iidcount-constant.md)|Общее количество содержащихся в интерфейсах, указанные параметрами шаблона идентификаторы интерфейсов *I0* через *I9*.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`I0`

`ChainInterfaces`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)