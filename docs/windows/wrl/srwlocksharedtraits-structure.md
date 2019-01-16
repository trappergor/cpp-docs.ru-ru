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
ms.openlocfilehash: af567fd333854519df4543ad24084e52cda4d96e
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336584"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits - структура

Описывает общие характеристики `SRWLock` класс в режим разделяемой блокировки.

## <a name="syntax"></a>Синтаксис

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя   | Описание:
------ | --------------------------------------------------------------------------
`Type` | Синоним для указателя на [SRWLOCK](srwlock-class.md) класса.

### <a name="public-methods"></a>Открытые методы

Имя                                                     | Описание
-------------------------------------------------------- | -----------------------------------------------------------------
[SRWLockSharedTraits::GetInvalidValue](#getinvalidvalue) | Извлекает `SRWLockSharedTraits` объект, который всегда является недопустимым.
[SRWLockSharedTraits::Unlock](#unlock)                   | Освобождает управлением указанного `SRWLock` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SRWLockSharedTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>SRWLockSharedTraits::GetInvalidValue

Извлекает `SRWLockSharedTraits` объект, который всегда является недопустимым.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор `SRWLockSharedTraits` объекта.

## <a name="unlock"></a>SRWLockSharedTraits::Unlock

Освобождает управлением указанного `SRWLock` объекта.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Параметры

*SRWLOCK*<br/>
Дескриптор `SRWLock` объекта.
