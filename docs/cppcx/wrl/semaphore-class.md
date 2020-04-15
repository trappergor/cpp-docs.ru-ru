---
title: Класс Semaphore
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
ms.openlocfilehash: e017b1b6316c4b6d49563d9a543950ab28961d90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359359"
---
# <a name="semaphore-class"></a>Класс Semaphore

Представляет объект синхронизации, который управляет общим ресурсом и поддерживает ограниченное число пользователей.

## <a name="syntax"></a>Синтаксис

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя       | Описание
---------- | ------------------------------------------------------
`SyncLock` | Синоним для класса, поддерживающего синхронные блокировки.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                               | Описание
---------------------------------- | ----------------------------------------------------
[Семафор:Семафор](#semaphore) | Инициализирует новый экземпляр класса `Semaphore`.

### <a name="public-methods"></a>Открытые методы

Имя                     | Описание
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[Семафор::Блокировка](#lock) | Ожидание, пока текущий объект или объект, связанный с указанной ручкой, не будут в состоянии сигнала или истек указанный интервал тайм-аута.

### <a name="public-operators"></a>Открытые операторы

Имя                                     | Описание
---------------------------------------- | ---------------------------------------------------------------------------------------
[Семафор:Оператор](#operator-assign) | Перемещение указанной ручки `Semaphore` с `Semaphore` объекта на текущий объект.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Semaphore`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Wrappers

## <a name="semaphorelock"></a><a name="lock"></a>Семафор::Блокировка

Ожидание, пока текущий `Semaphore` объект или объект, связанный с указанной ручкой, не будут в состоянии сигнала или истек указанный интервал тайм-аута.

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>Параметры

*Миллисекунд*<br/>
Интервал времени ожидания в миллисекундах. Значение по умолчанию равно INFINITE, что означает неограниченное время ожидания.

*H*<br/>
Ручка к `Semaphore` объекту.

### <a name="return-value"></a>Возвращаемое значение

`Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`;

## <a name="semaphoreoperator"></a><a name="operator-assign"></a>Семафор:Оператор

Перемещение указанной ручки `Semaphore` с `Semaphore` объекта на текущий объект.

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Rvalue-ссылка `Semaphore` на объект.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `Semaphore` текущий объект.

## <a name="semaphoresemaphore"></a><a name="semaphore"></a>Семафор:Семафор

Инициализирует новый экземпляр класса `Semaphore`.

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Ручка или rvalue-ссылка `Semaphore` на объект.
