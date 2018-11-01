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
ms.openlocfilehash: 84bfac08a944928ff91a7734cdbaccbe4d351e16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650753"
---
# <a name="mutextraits-structure"></a>MutexTraits - структура

Определяет общие характеристики [мьютекс](../windows/mutex-class1.md) класса.

## <a name="syntax"></a>Синтаксис

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

Имя                           | Описание
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
