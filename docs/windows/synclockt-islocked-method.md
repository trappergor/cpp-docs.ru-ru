---
title: Метод SyncLockT::IsLocked | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 067b3763e10b2bbb310b213f7d748e953ba2a902
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888479"
---
# <a name="synclocktislocked-method"></a>Метод SyncLockT::IsLocked
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
bool IsLocked() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если объект SyncLockT заблокирован; в противном случае — **false**.  
  
## <a name="remarks"></a>Примечания  
 Указывает, владеет ли текущий объект SyncLockT ресурсом; Объект SyncLockT является *заблокирован*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Класс SyncLockT](../windows/synclockt-class.md)