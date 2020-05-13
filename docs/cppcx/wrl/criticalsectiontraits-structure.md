---
title: CriticalSectionTraits - структура
ms.date: 09/26/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock method
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
ms.openlocfilehash: 05c93bf6a2765bd11489075067c627ab3c3ab691
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372583"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits - структура

Специализируется `CriticalSection` на объекте для поддержки либо недействительного критического раздела, либо функции для выпуска критического раздела.

## <a name="syntax"></a>Синтаксис

```
struct CriticalSectionTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя   | Описание
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | A, `typedef` определяющий указатель на критический раздел. `Type` определяется как `typedef CRITICAL_SECTION* Type;`.

### <a name="public-methods"></a>Открытые методы

Имя                                                       | Описание
---------------------------------------------------------- | -----------------
[КритическиеСекционныеобласти::GetInvalidValue](#getinvalidvalue) | Специализируется `CriticalSection` на шаблоне, чтобы шаблон всегда был недействительным.
[CriticalSectionTraits::Разблокировать](#unlock)                   | Специализируется `CriticalSection` на шаблоне таким образом, чтобы он поддерживал освобождение права собственности на указанный объект критического раздела.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CriticalSectionTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers:: HandleTraits

## <a name="criticalsectiontraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>КритическиеСекционныеобласти::GetInvalidValue

Специализируется `CriticalSection` на шаблоне, чтобы шаблон всегда был недействительным.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает указатель на недопустимую критическую секцию.

### <a name="remarks"></a>Remarks

Модификатор `Type` определен как `typedef CRITICAL_SECTION* Type;`.

## <a name="criticalsectiontraitsunlock"></a><a name="unlock"></a>CriticalSectionTraits::Разблокировать

Специализируется `CriticalSection` на шаблоне таким образом, чтобы он поддерживал освобождение права собственности на указанный объект критического раздела.

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>Параметры

*cs*<br/>
Указатель на объект критического сечения.

### <a name="remarks"></a>Remarks

Модификатор `Type` определен как `typedef CRITICAL_SECTION* Type;`.

Для получения дополнительной информации см. **функцию LeaveCriticalSection** в разделе **функции синхронизации** документации Windows API.
