---
title: "Метод SRWLock::LockExclusive | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
dev_langs: C++
helpviewer_keywords: LockExclusive method
ms.assetid: f361b672-fca6-45cc-a9b4-310cc0d23fdc
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 345a2a4b52e0bb0811709c71e9e0b1d4a9b4d494
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="srwlocklockexclusive-method"></a>Метод SRWLock::LockExclusive
Получает объект SRWLock в монопольном режиме.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
SyncLockExclusive LockExclusive();  
  
static SyncLockExclusive LockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `lock`  
 Указатель на объект SRWLock.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект SRWLock в монопольном режиме.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс SRWLock](../windows/srwlock-class.md)