---
title: SemaphoreTraits - структура
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock method
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
ms.openlocfilehash: e7bd2e5d0993c8e4be7223d98ffb1dbec14cbb74
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54337679"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits - структура

Определяет общие характеристики `Semaphore` объекта.

## <a name="syntax"></a>Синтаксис

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

Имя                               | Описание:
---------------------------------- | --------------------------------------
[SemaphoreTraits::Unlock](#unlock) | Элемент управления выпусков общего ресурса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="unlock"></a>SemaphoreTraits::Unlock

Элемент управления выпусков общего ресурса.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Дескриптор `Semaphore` объекта.

### <a name="remarks"></a>Примечания

Если обнаружено, операция разблокирования `Unlock()` выдает ошибку, которые указывают на причину сбоя.
