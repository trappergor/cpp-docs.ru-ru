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
ms.openlocfilehash: e67ecd6d5b4968af94ff1a82ad8be24e5b816298
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014251"
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