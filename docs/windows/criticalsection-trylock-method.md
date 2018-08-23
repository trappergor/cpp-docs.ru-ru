---
title: Метод CriticalSection::TryLock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 382dbdd2d0816d6ab0846acd0f8c164cd542114f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575845"
---
# <a name="criticalsectiontrylock-method"></a>Метод CriticalSection::TryLock

Пытается войти в критическую секцию без блокировки. Если вызов был успешным, вызывающий поток получает права владения критический раздел.

## <a name="syntax"></a>Синтаксис

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Параметры

*cs*  
Определенный пользователем объект критической секции.

## <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если критический раздел успешно передан или текущий поток уже владеет критическим разделом. Нуль, если другой поток уже владеет критическим разделом.

## <a name="remarks"></a>Примечания

Первый **TryLock** функции влияет на текущий объект критической секции. Второй **TryLock** функции влияет на определяемый пользователем критическую секцию.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс CriticalSection](../windows/criticalsection-class.md)