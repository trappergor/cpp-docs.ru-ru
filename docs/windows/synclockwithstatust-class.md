---
title: Класс SyncLockWithStatusT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT class
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 69676651c77175b55f4363b525a3ca3acb9be46d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437460"
---
# <a name="synclockwithstatust-class"></a>Класс SyncLockWithStatusT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename SyncTraits
>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>Параметры

*SyncTraits*<br/>
Тип, который может принимать монопольного или общее владение ресурсом.

## <a name="remarks"></a>Примечания

Представляет тип, который может занять монопольного или общее владение ресурсом.

**SyncLockWithStatusT** класс используется для реализации [мьютекс](../windows/mutex-class1.md) и [семафора](../windows/semaphore-class.md) классы.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор SyncLockWithStatusT::SyncLockWithStatusT](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Инициализирует новый экземпляр класса **SyncLockWithStatusT** класса.|

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор SyncLockWithStatusT::SyncLockWithStatusT](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Инициализирует новый экземпляр класса **SyncLockWithStatusT** класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод SyncLockWithStatusT::GetStatus](../windows/synclockwithstatust-getstatus-method.md)|Получает сведения о состоянии ожидания текущего **SyncLockWithStatusT** объекта.|
|[Метод SyncLockWithStatusT::IsLocked](../windows/synclockwithstatust-islocked-method.md)|Указывает ли текущий **SyncLockWithStatusT** объекта, которому принадлежит ресурс, то есть, **SyncLockWithStatusT** объект *заблокирован*.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[Элемент данных SyncLockWithStatusT::status_](../windows/synclockwithstatust-status-data-member.md)|Содержит результат базовой операции ожидания после операции блокирования объекта на основе текущего **SyncLockWithStatusT** объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)