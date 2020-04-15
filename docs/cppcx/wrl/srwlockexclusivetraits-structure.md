---
title: SRWLockExclusiveTraits - структура
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
ms.openlocfilehash: eb7b30915d6061e8470601df33fecec310d1bbca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374309"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits - структура

Описывает общие характеристики класса в эксклюзивном режиме блокировки. `SRWLock`

## <a name="syntax"></a>Синтаксис

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя   | Описание
------ | --------------------------------------------------------------------------
`Type` | Синоним указателя на класс [SRWLOCK.](srwlock-class.md)

### <a name="public-methods"></a>Открытые методы

Имя                                                        | Описание
----------------------------------------------------------- | --------------------------------------------------------------------
[SRWLockExclusiveTraits::GetInvalidValue](#getinvalidvalue) | Извлекает `SRWLockExclusiveTraits` объект, который всегда является недействительным.
[SRWLockExclusiveTraits::Разблокировка](#unlock)                   | Выпускает эксклюзивный контроль `SRWLock` указанного объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SRWLockExclusiveTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers:: HandleTraits

## <a name="srwlockexclusivetraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>SRWLockExclusiveTraits::GetInvalidValue

Извлекает `SRWLockExclusiveTraits` объект, который всегда является недействительным.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Пустой объект `SRWLockExclusiveTraits`.

## <a name="srwlockexclusivetraitsunlock"></a><a name="unlock"></a>SRWLockExclusiveTraits::Разблокировка

Выпускает эксклюзивный контроль `SRWLock` указанного объекта.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Параметры

*Srwlock*<br/>
Обработка `SRWLock` объекта.
