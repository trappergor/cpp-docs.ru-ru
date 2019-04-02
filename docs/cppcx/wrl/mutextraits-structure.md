---
title: MutexTraits - структура
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock method
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
ms.openlocfilehash: 9bc4071e5699610a664cbf01ca3e7d36d7effc5e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785069"
---
# <a name="mutextraits-structure"></a>MutexTraits - структура

Определяет общие характеристики [мьютекс](mutex-class.md) класса.

## <a name="syntax"></a>Синтаксис

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

name                           | Описание
------------------------------ | ------------------------------------------------
[MutexTraits::Unlock](#unlock) | Освобождает управлением общего ресурса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="unlock"></a>Метод MutexTraits::Unlock

Освобождает управлением общего ресурса.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Дескриптор объекта mutex.
