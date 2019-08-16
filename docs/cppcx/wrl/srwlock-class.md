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
ms.openlocfilehash: 079f1abe652d8c1610a084f5e1158cc5798d61c4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498295"
---
# <a name="srwlock-class"></a>SRWLock - класс

Представляет тонкую блокировку чтения и записи.

## <a name="syntax"></a>Синтаксис

```cpp
class SRWLock;
```

## <a name="remarks"></a>Примечания

Упрощенная блокировка потоков чтения/записи используется для синхронизации доступа между потоками с объектом или ресурсом. Дополнительные сведения см. в разделе [функции синхронизации](/windows/win32/Sync/synchronization-functions).

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

name                | Описание
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | Синоним для `SRWLock` объекта, полученного в монопольном режиме.
`SyncLockShared`    | Синоним для `SRWLock` объекта, полученного в режиме общего доступа.

### <a name="public-constructors"></a>Открытые конструкторы

name                                     | Описание
---------------------------------------- | --------------------------------------------------
[SRWLock:: SRWLock](#srwlock-constructor) | Инициализирует новый экземпляр класса `SRWLock`.
[SRWLock:: ~ SRWLock](#tilde-srwlock)      | Выполняет деинициализацию экземпляра `SRWLock` класса.

### <a name="public-methods"></a>Открытые методы

name                                           | Описание
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock:: LockExclusive](#lockexclusive)       | `SRWLock` Получает объект в монопольном режиме.
[SRWLock:: LockShared](#lockshared)             | `SRWLock` Получает объект в общем режиме.
[SRWLock:: TryLockExclusive](#trylockexclusive) | Пытается получить `SRWLock` объект в монопольном режиме для текущего или указанного `SRWLock` объекта.
[SRWLock:: TryLockShared](#trylockshared)       | Пытается получить `SRWLock` объект в общем режиме для текущего или указанного `SRWLock` объекта.

### <a name="protected-data-member"></a>Защищенный элемент данных

name                                      | Описание
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock:: SRWLock_](#srwlock-data-member) | Содержит базовую переменную блокировки для текущего `SRWLock` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SRWLock`

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс. h

**Пространство имен:** Программы Microsoft:: WRL:: оболочки

## <a name="tilde-srwlock"></a>SRWLock:: ~ SRWLock

Выполняет деинициализацию экземпляра `SRWLock` класса.

```cpp
~SRWLock();
```

## <a name="lockexclusive"></a>SRWLock:: LockExclusive

`SRWLock` Получает объект в монопольном режиме.

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

## <a name="lockshared"></a>SRWLock:: LockShared

`SRWLock` Получает объект в общем режиме.

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

`SRWLock` Объект в общем режиме.

## <a name="srwlock-constructor"></a>SRWLock:: SRWLock

Инициализирует новый экземпляр класса `SRWLock`.

```cpp
SRWLock();
```

## <a name="srwlock-data-member"></a>SRWLock:: SRWLock_

Содержит базовую переменную блокировки для текущего `SRWLock` объекта.

```cpp
SRWLOCK SRWLock_;
```

## <a name="trylockexclusive"></a>SRWLock:: TryLockExclusive

Пытается получить `SRWLock` объект в монопольном режиме для текущего или указанного `SRWLock` объекта. Если вызов выполнен успешно, вызывающий поток принимает владение блокировкой.

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

В случае успеха `SRWLock` объект в монопольном режиме и вызывающий поток принимает владение блокировкой. В противном `SRWLock` случае — объект, состояние которого является недопустимым.

## <a name="trylockshared"></a>SRWLock:: TryLockShared

Пытается получить `SRWLock` объект в общем режиме для текущего или указанного `SRWLock` объекта.

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

В случае успеха `SRWLock` объект в общем режиме и вызывающий поток принимает владение блокировкой. В противном `SRWLock` случае — объект, состояние которого является недопустимым.
