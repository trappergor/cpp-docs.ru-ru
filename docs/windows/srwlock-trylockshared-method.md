---
title: Метод SRWLock::TryLockShared | Документы Microsoft
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
ms.openlocfilehash: 19ff9324f946f48f201678f9c9e7403ba774b2c0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892287"
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