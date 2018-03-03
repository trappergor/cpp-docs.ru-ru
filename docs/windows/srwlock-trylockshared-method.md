---
title: "Метод SRWLock::TryLockShared | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs:
- C++
helpviewer_keywords:
- TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c36657b5c732055260dc77471e109961a66c144
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="srwlocktrylockshared-method"></a>Метод SRWLock::TryLockShared
Пытается получить объект SRWLock в режиме общего доступа для текущей или заданной объекта SRWLock.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `lock`  
 Указатель на объект SRWLock.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения объекта SRWLock в режиме общего доступа и вызывающий поток становится владельцем блокировки. В противном случае SRWLock объекта, состояние которого является недопустимым.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс SRWLock](../windows/srwlock-class.md)