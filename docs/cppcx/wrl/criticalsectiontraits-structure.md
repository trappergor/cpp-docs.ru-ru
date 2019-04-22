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
ms.openlocfilehash: ce904ecbd9a5855c63fd43f07f88c215cef544ae
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785916"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits - структура

Специализируется `CriticalSection` объекта для поддержки недопустимую критическую секцию или функцию для освобождения критического раздела.

## <a name="syntax"></a>Синтаксис

```
struct CriticalSectionTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

name   | Описание
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | Объект `typedef` указатель, определяющий критической секции. `Type` определяется как `typedef CRITICAL_SECTION* Type;`.

### <a name="public-methods"></a>Открытые методы

name                                                       | Описание
---------------------------------------------------------- | -----------------
[CriticalSectionTraits::GetInvalidValue](#getinvalidvalue) | Специализируется `CriticalSection` шаблона, чтобы шаблон всегда является недопустимым.
[CriticalSectionTraits::Unlock](#unlock)                   | Специализируется `CriticalSection` шаблона, так что он поддерживает снятию владения объектом указанного критический раздел.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CriticalSectionTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>CriticalSectionTraits::GetInvalidValue

Специализируется `CriticalSection` шаблона, чтобы шаблон всегда является недопустимым.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает указатель на недопустимую критическую секцию.

### <a name="remarks"></a>Примечания

Модификатор `Type` определен как `typedef CRITICAL_SECTION* Type;`.

## <a name="unlock"></a>CriticalSectionTraits::Unlock

Специализируется `CriticalSection` шаблона, так что он поддерживает снятию владения объектом указанного критический раздел.

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>Параметры

*cs*<br/>
Указатель на объект критической секции.

### <a name="remarks"></a>Примечания

Модификатор `Type` определен как `typedef CRITICAL_SECTION* Type;`.

Дополнительные сведения см. в разделе **функция LeaveCriticalSection** в **функций синхронизации** раздел документации Windows API.
