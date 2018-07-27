---
title: Метод SRWLock::TryLockExclusive | Документы Microsoft
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
ms.openlocfilehash: 1cc9ee8a63d7403c3de408c924eeab07f1d0efa1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892661"
---
# <a name="srwlocktrylockexclusive-method"></a>Метод SRWLock::TryLockExclusive
Пытается получить объект SRWLock в монопольном режиме для текущей или заданной объекта SRWLock. При успешном вызове вызывающий поток становится владельцем блокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `lock`  
 Указатель на объект SRWLock.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения объекта SRWLock в монопольном режиме и что вызывающий поток становится владельцем блокировки. В противном случае SRWLock объекта, состояние которого является недопустимым.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс SRWLock](../windows/srwlock-class.md)