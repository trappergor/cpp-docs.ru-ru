---
title: SRWLockSharedTraits - структура
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock method
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
ms.openlocfilehash: 0dc43d4b9c16145ed7a5abe03cddb598c59b1e94
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374289"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits - структура

Описывает общие характеристики класса в режиме общего блокировки. `SRWLock`

## <a name="syntax"></a>Синтаксис

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя   | Описание
------ | --------------------------------------------------------------------------
`Type` | Синоним указателя на класс [SRWLOCK.](srwlock-class.md)

### <a name="public-methods"></a>Открытые методы

Имя                                                     | Описание
-------------------------------------------------------- | -----------------------------------------------------------------
[SRWLockSharedTraits::GetInvalidValue](#getinvalidvalue) | Извлекает `SRWLockSharedTraits` объект, который всегда является недействительным.
[SRWLockSharedTraits::Разблокировка](#unlock)                   | Выпускает эксклюзивный контроль `SRWLock` указанного объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SRWLockSharedTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers:: HandleTraits

## <a name="srwlocksharedtraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>SRWLockSharedTraits::GetInvalidValue

Извлекает `SRWLockSharedTraits` объект, который всегда является недействительным.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к `SRWLockSharedTraits` объекту.

## <a name="srwlocksharedtraitsunlock"></a><a name="unlock"></a>SRWLockSharedTraits::Разблокировка

Выпускает эксклюзивный контроль `SRWLock` указанного объекта.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Параметры

*Srwlock*<br/>
Ручка к `SRWLock` объекту.
