---
title: Метод SyncLockWithStatusT::IsLocked | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebe723811efe62efa85a1cc2fa35736689306c7e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645637"
---
# <a name="synclockwithstatustislocked-method"></a>Метод SyncLockWithStatusT::IsLocked
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
bool IsLocked() const;  
```  
  
## <a name="remarks"></a>Примечания  
 Указывает ли текущий **SyncLockWithStatusT** объекта, которому принадлежит ресурс, то есть, **SyncLockWithStatusT** объект *заблокирован*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если **SyncLockWithStatusT** объектов заблокирован; в противном случае — значение **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)