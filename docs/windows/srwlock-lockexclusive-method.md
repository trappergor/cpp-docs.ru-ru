---
title: Метод SRWLock::LockExclusive | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
dev_langs:
- C++
helpviewer_keywords:
- LockExclusive method
ms.assetid: f361b672-fca6-45cc-a9b4-310cc0d23fdc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 36ae694365b58cb10666e5d8af67269b2c4f125c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889375"
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