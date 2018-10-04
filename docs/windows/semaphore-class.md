---
title: Класс семафора | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 78fa5b68bcb55f7d062c1732ab6c30fbe84c22d8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789219"
---
# <a name="semaphore-class"></a>Semaphore - класс

Представляет объект синхронизации, который управляет общим ресурсом и поддерживает ограниченное число пользователей.

## <a name="syntax"></a>Синтаксис

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя       | Описание
---------- | ------------------------------------------------------
`SyncLock` | Синоним для класса, поддерживающего синхронной блокировки.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                               | Описание
---------------------------------- | ----------------------------------------------------
[Semaphore::Semaphore](#semaphore) | Инициализирует новый экземпляр класса `Semaphore`.

### <a name="public-methods"></a>Открытые методы

Имя                     | Описание
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[Semaphore::LOCK](#lock) | Ожидает, пока текущий объект или объект, связанный с указанным дескриптором, находится в сигнальном состоянии или истечет указанный интервал времени ожидания.

### <a name="public-operators"></a>Открытые операторы

Имя                                     | Описание
---------------------------------------- | ---------------------------------------------------------------------------------------
[Semaphore::operator =](#operator-assign) | Перемещает указанный дескриптор из `Semaphore` объект с текущим `Semaphore` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Semaphore`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="lock"></a>Semaphore::LOCK

Только после текущего объекта, или `Semaphore` объект, связанный с указанным дескриптором, находится в сигнальном состоянии или истечет указанный интервал времени ожидания.

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

*в миллисекундах*<br/>
Интервал времени ожидания в миллисекундах. Значение по умолчанию равно INFINITE, что означает неограниченное время ожидания.

*h*<br/>
Дескриптор `Semaphore` объекта.

### <a name="return-value"></a>Возвращаемое значение

`Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="operator-assign"></a>Semaphore::operator =

Перемещает указанный дескриптор из `Semaphore` объект с текущим `Semaphore` объекта.

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Ссылка rvalue на `Semaphore` объекта.

### <a name="return-value"></a>Возвращаемое значение

Ссылку на текущий `Semaphore` объекта.

## <a name="semaphore"></a>Semaphore::Semaphore

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

*h*<br/>
Дескриптор или rvalue ссылка на `Semaphore` объекта.
