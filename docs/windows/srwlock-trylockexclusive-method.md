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
ms.openlocfilehash: 993031604469aa09608f936f260869a3b53dbc9c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652774"
---
# <a name="srwlocktrylockexclusive-method"></a>Метод SRWLock::TryLockExclusive
Пытается получить **SRWLock** объекта в монопольном режиме для текущей или заданной **SRWLock** объекта. Если вызов был успешным, вызывающий поток принимает владельца блокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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