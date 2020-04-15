---
title: Класс SyncLockWithStatusT
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT class
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT, constructor
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
ms.openlocfilehash: 77bcb8336e4650de7ed01a067fa1bdd7ec0ba3e8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374266"
---
# <a name="synclockwithstatust-class"></a>Класс SyncLockWithStatusT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>Параметры

*SyncTraits*<br/>
Тип, который может иметь исключительное или совместное владение ресурсом.

## <a name="remarks"></a>Remarks

Представляет тип, который может иметь исключительное или совместное владение ресурсом.

Класс `SyncLockWithStatusT` используется для реализации классов [Mutex](mutex-class.md) и [Semaphore.](semaphore-class.md)

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                             | Описание
---------------------------------------------------------------- | --------------------------------------------------------------
[SynclockWithstatust::SynclockWithstatust](#synclockwithstatust) | Инициализирует новый экземпляр класса `SyncLockWithStatusT`.

### <a name="protected-constructors"></a>Защищенные конструкторы

Имя                                                             | Описание
---------------------------------------------------------------- | --------------------------------------------------------------
[SynclockWithstatust::SynclockWithstatust](#synclockwithstatust) | Инициализирует новый экземпляр класса `SyncLockWithStatusT`.

### <a name="public-methods"></a>Открытые методы

Имя                                         | Описание
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[SynclockWithstatust::GetStatus](#getstatus) | Извлекает состояние ожидания текущего `SyncLockWithStatusT` объекта.
[SynclockWithstatust::Заблокирован](#islocked)   | Указывает, является `SyncLockWithStatusT` ли текущий объект владельцем ресурса; то есть, `SyncLockWithStatusT` объект *заблокирован.*

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                                    | Описание
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[SynclockWithstatust::status_](#status) | Сохраняет результат основной операции ожидания после операции блокировки на `SyncLockWithStatusT` объекте, основанном на текущем объекте.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Обертывания::D

## <a name="synclockwithstatustgetstatus"></a><a name="getstatus"></a>SynclockWithstatust::GetStatus

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>Возвращаемое значение

Результат операции ожидания на объекте, основанном `SyncLockWithStatusT` на классе, например [Mutex](mutex-class.md) или [Semaphore.](semaphore-class.md) Ноль (0) указывает на то, что операция ожидания вернула сигнализированное состояние; в противном случае произошло другое состояние, например, истечение времени.

### <a name="remarks"></a>Remarks

Извлекает состояние ожидания текущего `SyncLockWithStatusT` объекта.

Функция GetStatus() получает значение [базового](#status) status_ члена данных. Когда объект, основанный на `SyncLockWithStatusT` классе, выполняет операцию блокировки, объект сначала ждет, когда объект станет доступным. Результат этой операции ожидания хранится `status_` в члене данных. Возможные значения члена `status_` данных — это значения возврата операции ожидания. Для получения дополнительной информации смотрите `WaitForSingleObjectEx()` значения возврата функции в библиотеке MSDN.

## <a name="synclockwithstatustislocked"></a><a name="islocked"></a>SynclockWithstatust::Заблокирован

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>Remarks

Указывает, является `SyncLockWithStatusT` ли текущий объект владельцем ресурса; то есть, `SyncLockWithStatusT` объект *заблокирован.*

### <a name="return-value"></a>Возвращаемое значение

**верно,** `SyncLockWithStatusT` если объект заблокирован; в противном случае, **ложные**.

## <a name="synclockwithstatuststatus_"></a><a name="status"></a>SynclockWithstatust::status_

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
DWORD status_;
```

### <a name="remarks"></a>Remarks

Сохраняет результат основной операции ожидания после операции блокировки на `SyncLockWithStatusT` объекте, основанном на текущем объекте.

## <a name="synclockwithstatustsynclockwithstatust"></a><a name="synclockwithstatust"></a>SynclockWithstatust::SynclockWithstatust

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
SyncLockWithStatusT(
   _Inout_ SyncLockWithStatusT&& other
);

explicit SyncLockWithStatusT(
   typename SyncTraits::Type sync,
   DWORD status
);
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Rvalue-ссылка на `SyncLockWithStatusT` другой объект.

*Синхронизации*<br/>
Ссылка на `SyncLockWithStatusT` другой объект.

*состояние*<br/>
Значение [status_](#status) данных, являющийся членом *другого* параметра или параметра *синхронизации.*

### <a name="remarks"></a>Remarks

Инициализирует новый экземпляр класса `SyncLockWithStatusT`.

Первый конструктор `SyncLockWithStatusT` инициализирует `SyncLockWithStatusT` текущий объект от другого указанного `SyncLockWithStatusT` по параметру *другого,* а затем аннулирует другой объект. Второй конструктор — `protected`это, и инициализирует текущий `SyncLockWithStatusT` объект в недействительное состояние.
