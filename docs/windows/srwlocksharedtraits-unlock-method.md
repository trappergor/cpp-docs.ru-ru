---
title: Метод SRWLockSharedTraits::Unlock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 33cdead9-1900-4094-b18e-38fcf1a0bd28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e00b898fc60953896a9c0d2b7a124e195d3bcbf1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593172"
---
# <a name="srwlocksharedtraitsunlock-method"></a>Метод SRWLockSharedTraits::Unlock

Освобождает управлением указанного `SRWLock` объекта.

## <a name="syntax"></a>Синтаксис

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Параметры

*SRWLOCK*  
Дескриптор `SRWLock` объекта.

## <a name="return-value"></a>Возвращаемое значение

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>См. также

[Структура SRWLockSharedTraits](../windows/srwlocksharedtraits-structure.md)