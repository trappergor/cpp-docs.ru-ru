---
title: SRWLOCK-класс | Документация Майкрософт
ms.custom: ''
ms.date: 09/25/2018
ms.technology:
- cpp-windows
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 771a375d46177bb3b9d263f0a5221039bb963bc2
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48233974"
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

Имя                | Описание
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | Синоним для `SRWLock` объекта, получившего в монопольном режиме.
`SyncLockShared`    | Синоним для `SRWLock` объекта, получившего в режиме общего доступа.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                     | Описание
---------------------------------------- | --------------------------------------------------
[SRWLock::SRWLock](#srwlock-constructor) | Инициализирует новый экземпляр класса `SRWLock`.
[SRWLock:: ~ SRWLock](#tilde-srwlock)      | Отменяет инициализацию экземпляра `SRWLock` класса.

### <a name="public-methods"></a>Открытые методы

Имя                                           | Описание
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

**Пространство имен:** Microsoft::wrl:: wrappers

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
