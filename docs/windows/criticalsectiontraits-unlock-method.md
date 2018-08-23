---
title: Метод CriticalSectionTraits::Unlock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 003bb9c845ef8124ade1262a25368d3d4cb34fa6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606435"
---
# <a name="criticalsectiontraitsunlock-method"></a>Метод CriticalSectionTraits::Unlock

Специализируется `CriticalSection` шаблона, так что он поддерживает снятию владения объектом указанного критический раздел.

## <a name="syntax"></a>Синтаксис

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>Параметры

*cs*  
Указатель на объект критической секции.

## <a name="remarks"></a>Примечания

Модификатор `Type` определен как `typedef CRITICAL_SECTION* Type;`.

Дополнительные сведения см. в разделе **функция LeaveCriticalSection** в **функций синхронизации** раздел документации Windows API.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>См. также

[Структура CriticalSectionTraits](../windows/criticalsectiontraits-structure.md)