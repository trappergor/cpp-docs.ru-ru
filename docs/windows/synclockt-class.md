---
title: Synclockt-класс | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e8589c43d49709842a745464d2727860ccd2c1e2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609681"
---
# <a name="synclockt-class"></a>SyncLockT - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename SyncTraits
>
class SyncLockT;
```

### <a name="parameters"></a>Параметры

*SyncTraits*  
Тип, который может стать владельцем ресурса.

## <a name="remarks"></a>Примечания

Представляет тип, который может занять монопольного или общее владение ресурсом.

**SyncLockT** класс используется, например, чтобы реализовать [SRWLock](../windows/srwlock-class.md) класса.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор SyncLockT::SyncLockT](../windows/synclockt-synclockt-constructor.md)|Инициализирует новый экземпляр класса **SyncLockT** класса.|
|[Деструктор SyncLockT::~SyncLockT](../windows/synclockt-tilde-synclockt-destructor.md)|Отменяет инициализацию экземпляра **SyncLockT** класса.|

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор SyncLockT::SyncLockT](../windows/synclockt-synclockt-constructor.md)|Инициализирует новый экземпляр класса **SyncLockT** класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Метод SyncLockT::IsLocked](../windows/synclockt-islocked-method.md)|Указывает ли текущий **SyncLockT** объекта, которому принадлежит ресурс, то есть, **SyncLockT** объект *заблокирован*.|
|[Метод SyncLockT::Unlock](../windows/synclockt-unlock-method.md)|Управление ресурсы, удерживаемые текущим **SyncLockT** объекта, если таковые имеются.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание:|
|----------|-----------------|
|[Элемент данных SyncLockT::sync_](../windows/synclockt-sync-data-member.md)|Удерживает базовый ресурс, представленный **SyncLockT** класса.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SyncLockT`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)  
[Класс SRWLock](../windows/srwlock-class.md)