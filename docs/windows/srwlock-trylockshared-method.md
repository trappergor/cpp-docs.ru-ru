---
title: Метод SRWLock::TryLockShared | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs:
- C++
helpviewer_keywords:
- TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bcad153145432997841753828b3b01b728ff365d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608177"
---
# <a name="srwlocktrylockshared-method"></a>Метод SRWLock::TryLockShared

Пытается получить **SRWLock** объект в режиме общего доступа для текущей или заданной **SRWLock** объекта.

## <a name="syntax"></a>Синтаксис

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*  
Указатель на **SRWLock** объекта.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения **SRWLock** объекта в режиме общего доступа и вызывающий поток принимает владельца блокировки. В противном случае **SRWLock** объект, состояние которого является недопустимым.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс SRWLock](../windows/srwlock-class.md)