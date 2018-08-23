---
title: Метод SRWLock::TryLockExclusive | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
dev_langs:
- C++
helpviewer_keywords:
- TryLockExclusive method
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2ec8275b1db692410677276e762f79ccf23548cc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606235"
---
# <a name="srwlocktrylockexclusive-method"></a>Метод SRWLock::TryLockExclusive

Пытается получить **SRWLock** объекта в монопольном режиме для текущей или заданной **SRWLock** объекта. Если вызов был успешным, вызывающий поток принимает владельца блокировки.

## <a name="syntax"></a>Синтаксис

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*  
Указатель на **SRWLock** объекта.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения **SRWLock** объекта в монопольном режиме и вызывающий поток принимает владельца блокировки. В противном случае **SRWLock** объект, состояние которого является недопустимым.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс SRWLock](../windows/srwlock-class.md)