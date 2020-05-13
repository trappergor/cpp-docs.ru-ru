---
title: SyncLockT - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::sync_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockT class
- Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockT::sync_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT, constructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT, destructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock method
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
ms.openlocfilehash: 52c4404fa28f680a9a7a4592d03f535e8406d1a4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374284"
---
# <a name="synclockt-class"></a>SyncLockT - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>Параметры

*SyncTraits*<br/>
Тип, который может взять на себя ответственность за ресурс.

## <a name="remarks"></a>Remarks

Представляет тип, который может иметь исключительное или совместное владение ресурсом.

Класс `SyncLockT` используется, например, для реализации класса [SRWLock.](srwlock-class.md)

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                      | Описание
----------------------------------------- | ----------------------------------------------------
[SyncLockT::SyncLockT](#synclockt)        | Инициализирует новый экземпляр класса `SyncLockT`.
[SyncLockT::-SyncLockT](#tilde-synclockt) | Деприиратизирует экземпляр `SyncLockT` класса.

### <a name="protected-constructors"></a>Защищенные конструкторы

Имя                               | Описание
---------------------------------- | ----------------------------------------------------
[SyncLockT::SyncLockT](#synclockt) | Инициализирует новый экземпляр класса `SyncLockT`.

### <a name="public-methods"></a>Открытые методы

Имя                             | Описание
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[SyncLockT::Заблокирован](#islocked) | Указывает, является `SyncLockT` ли текущий объект владельцем ресурса; то есть, `SyncLockT` объект *заблокирован.*
[SyncLockT::Разблокировка](#unlock)     | Выпускает контроль ресурса, удерживаемого текущим `SyncLockT` объектом, если такового.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                      | Описание
------------------------- | -------------------------------------------------------------------
[SyncLockT::sync_](#sync) | Сохраняет базовый ресурс, представленный классом. `SyncLockT`

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SyncLockT`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Обертывания::D

## <a name="synclocktsynclockt"></a><a name="tilde-synclockt"></a>SyncLockT::-SyncLockT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
~SyncLockT();
```

### <a name="remarks"></a>Remarks

Деприиратизирует экземпляр `SyncLockT` класса.

Этот деструктор также открывает `SyncLockT` текущий экземпляр.

## <a name="synclocktislocked"></a><a name="islocked"></a>SyncLockT::Заблокирован

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** `SyncLockT` если объект заблокирован; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Указывает, является `SyncLockT` ли текущий объект владельцем ресурса; то есть, `SyncLockT` объект *заблокирован.*

## <a name="synclocktsync_"></a><a name="sync"></a>SyncLockT::sync_

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>Remarks

Сохраняет базовый ресурс, представленный классом. `SyncLockT`

## <a name="synclocktsynclockt"></a><a name="synclockt"></a>SyncLockT::SyncLockT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()
);
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Rvalue-ссылка на `SyncLockT` другой объект.

*Синхронизации*<br/>
Ссылка на `SyncLockWithStatusT` другой объект.

### <a name="remarks"></a>Remarks

Инициализирует новый экземпляр класса `SyncLockT`.

Первый конструктор `SyncLockT` инициализирует `SyncLockT` текущий объект с другого объекта, `SyncLockT` указанного по параметру *другого,* а затем аннулирует другой объект. Второй конструктор — `protected`это, и инициализирует текущий `SyncLockT` объект в недействительное состояние.

## <a name="synclocktunlock"></a><a name="unlock"></a>SyncLockT::Разблокировка

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
void Unlock();
```

### <a name="remarks"></a>Remarks

Выпускает контроль ресурса, удерживаемого текущим `SyncLockT` объектом, если такового.
