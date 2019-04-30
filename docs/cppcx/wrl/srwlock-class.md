---
title: SRWLock - класс
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock_
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::~SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
helpviewer_keywords:
- Microsoft::WRL::Wrappers::SRWLock class
- Microsoft::WRL::Wrappers::SRWLock::LockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::LockShared method
- Microsoft::WRL::Wrappers::SRWLock::SRWLock, constructor
- Microsoft::WRL::Wrappers::SRWLock::SRWLock_ data member
- Microsoft::WRL::Wrappers::SRWLock::~SRWLock, destructor
- Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::TryLockShared method
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
ms.openlocfilehash: 6d4a504d9465c858af59a88cf0ef611bf88c3fde
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403096"
---
# <a name="srwlock-class"></a>SRWLock - класс

Представляет тонкую блокировку чтения и записи.

## <a name="syntax"></a>Синтаксис

```cpp
class SRWLock;
```

## <a name="remarks"></a>Примечания

Блокировки потоков чтения/записи используется для синхронизации доступа между потоками для объекта или ресурса. Дополнительные сведения см. в разделе [функций синхронизации](/windows/desktop/Sync/synchronization-functions).

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

name                | Описание
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | Синоним для `SRWLock` объекта, получившего в монопольном режиме.
`SyncLockShared`    | Синоним для `SRWLock` объекта, получившего в режиме общего доступа.

### <a name="public-constructors"></a>Открытые конструкторы

name                                     | Описание
---------------------------------------- | --------------------------------------------------
[SRWLock::SRWLock](#srwlock-constructor) | Инициализирует новый экземпляр класса `SRWLock`.
[SRWLock:: ~ SRWLock](#tilde-srwlock)      | Отменяет инициализацию экземпляра `SRWLock` класса.

### <a name="public-methods"></a>Открытые методы

name                                           | Описание
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock::LockExclusive](#lockexclusive)       | Получает `SRWLock` объекта в монопольном режиме.
[SRWLock::LockShared](#lockshared)             | Получает `SRWLock` объект в режиме общего доступа.
[SRWLock::TryLockExclusive](#trylockexclusive) | Пытается получить `SRWLock` объекта в монопольном режиме для текущей или заданной `SRWLock` объекта.
[SRWLock::TryLockShared](#trylockshared)       | Пытается получить `SRWLock` объект в режиме общего доступа для текущей или заданной `SRWLock` объекта.

### <a name="protected-data-member"></a>Защищенные данные-член

name                                      | Описание
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock::SRWLock_](#srwlock-data-member) | Содержит базовой переменной блокировки для текущего `SRWLock` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SRWLock`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers

## <a name="tilde-srwlock"></a>SRWLock:: ~ SRWLock

Отменяет инициализацию экземпляра `SRWLock` класса.

```cpp
~SRWLock();
```

## <a name="lockexclusive"></a>SRWLock::LockExclusive

Получает `SRWLock` объекта в монопольном режиме.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Указатель на `SRWLock` объект.

### <a name="return-value"></a>Возвращаемое значение

`SRWLock` Объект в монопольном режиме.

## <a name="lockshared"></a>SRWLock::LockShared

Получает `SRWLock` объект в режиме общего доступа.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Указатель на `SRWLock` объект.

### <a name="return-value"></a>Возвращаемое значение

`SRWLock` Объект в режиме общего доступа.

## <a name="srwlock-constructor"></a>SRWLock::SRWLock

Инициализирует новый экземпляр класса `SRWLock`.

```cpp
SRWLock();
```

## <a name="srwlock-data-member"></a>SRWLock::SRWLock_

Содержит базовой переменной блокировки для текущего `SRWLock` объекта.

```cpp
SRWLOCK SRWLock_;
```

## <a name="trylockexclusive"></a>SRWLock::TryLockExclusive

Пытается получить `SRWLock` объекта в монопольном режиме для текущей или заданной `SRWLock` объекта. Если вызов был успешным, вызывающий поток принимает владельца блокировки.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Указатель на `SRWLock` объект.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения `SRWLock` объекта в монопольном режиме и вызывающий поток принимает владельца блокировки. В противном случае `SRWLock` объект, состояние которого является недопустимым.

## <a name="trylockshared"></a>SRWLock::TryLockShared

Пытается получить `SRWLock` объект в режиме общего доступа для текущей или заданной `SRWLock` объекта.

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Указатель на `SRWLock` объект.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения `SRWLock` объекта в режиме общего доступа и вызывающий поток принимает владельца блокировки. В противном случае `SRWLock` объект, состояние которого является недопустимым.
