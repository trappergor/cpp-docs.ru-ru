---
title: Метод CriticalSection::Lock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f13af220107ba8d5bc5c26c65c2034f125a39454
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382457"
---
# <a name="criticalsectionlock-method"></a>Метод CriticalSection::Lock

Ожиданий владения объектом указанного критический раздел. Функция возвращает при предоставлении владельцем вызывающего потока.

## <a name="syntax"></a>Синтаксис

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Параметры

*cs*<br/>
Определенный пользователем объект критической секции.

## <a name="return-value"></a>Возвращаемое значение

Объект блокировки, который можно использовать, чтобы разблокировать текущую критическую секцию.

## <a name="remarks"></a>Примечания

Первый **блокировки** функции влияет на текущий объект критической секции. Второй **блокировки** функции влияет на определяемый пользователем критическую секцию.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс CriticalSection](../windows/criticalsection-class.md)