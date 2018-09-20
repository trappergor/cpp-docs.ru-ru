---
title: Метод SemaphoreTraits::Unlock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c9519fb79bf8229578319fc1f3890f5d2e19442a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448299"
---
# <a name="semaphoretraitsunlock-method"></a>Метод SemaphoreTraits::Unlock

Элемент управления выпусков общего ресурса.

## <a name="syntax"></a>Синтаксис

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Дескриптор **семафора** объекта.

## <a name="remarks"></a>Примечания

Если обнаружено, операция разблокирования **Unlock()** выдает ошибку, которые указывают на причину сбоя.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>См. также

[Структура SemaphoreTraits](../windows/semaphoretraits-structure.md)