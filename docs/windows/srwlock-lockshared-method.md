---
title: Метод SRWLock::LockShared | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
dev_langs:
- C++
helpviewer_keywords:
- LockShared method
ms.assetid: 9d826a5c-b6a2-4430-ac85-d5753cbca889
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 62667d20e40e04f9202fcb5dfa2f1688b98a3c2d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429049"
---
# <a name="srwlocklockshared-method"></a>Метод SRWLock::LockShared

Получает **SRWLock** объект в режиме общего доступа.

## <a name="syntax"></a>Синтаксис

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Указатель на **SRWLock** объекта.

## <a name="return-value"></a>Возвращаемое значение

**SRWLock** объект в режиме общего доступа.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс SRWLock](../windows/srwlock-class.md)