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
ms.openlocfilehash: 4005f0dc1f75b79650963efc9a6f9f7522bc3395
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476470"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits - структура

Описывает общие характеристики `SRWLock` класс в режиме эксклюзивной блокировки.

## <a name="syntax"></a>Синтаксис

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя   | Описание
------ | --------------------------------------------------------------------------
`Type` | Синоним для указателя на [SRWLOCK](../windows/srwlock-class.md) класса.

### <a name="public-methods"></a>Открытые методы

Имя                                                        | Описание
----------------------------------------------------------- | --------------------------------------------------------------------
[SRWLockExclusiveTraits::GetInvalidValue](#getinvalidvalue) | Извлекает `SRWLockExclusiveTraits` объект, который всегда является недопустимым.
[SRWLockExclusiveTraits::Unlock](#unlock)                   | Освобождает управлением указанного `SRWLock` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SRWLockExclusiveTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>SRWLockExclusiveTraits::GetInvalidValue

Извлекает `SRWLockExclusiveTraits` объект, который всегда является недопустимым.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Пустой объект `SRWLockExclusiveTraits`

## <a name="unlock"></a>SRWLockExclusiveTraits::Unlock

Освобождает управлением указанного `SRWLock` объекта.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Параметры

*SRWLOCK*<br/>
Дескриптор `SRWLock` объекта.
