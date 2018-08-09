---
title: Метод SyncLockT::IsLocked | Документация Майкрософт
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
ms.openlocfilehash: 5bfbd3418af731edf826debd9d6663095be706b8
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641523"
---
# <a name="synclocktislocked-method"></a>Метод SyncLockT::IsLocked
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
bool IsLocked() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если **SyncLockT** объектов заблокирован; в противном случае — значение **false**.  
  
## <a name="remarks"></a>Примечания  
 Указывает ли текущий **SyncLockT** объекта, которому принадлежит ресурс, то есть, **SyncLockT** объект *заблокирован*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Класс SyncLockT](../windows/synclockt-class.md)