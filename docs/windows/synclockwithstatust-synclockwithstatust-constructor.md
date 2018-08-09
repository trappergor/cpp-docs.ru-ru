---
title: Конструктор SyncLockWithStatusT::SyncLockWithStatusT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT, constructor
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 21ce2054cabf257594cb3fa376236b9a1e504a59
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647759"
---
# <a name="synclockwithstatustsynclockwithstatust-constructor"></a>Конструктор SyncLockWithStatusT::SyncLockWithStatusT
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
SyncLockWithStatusT(  
   _Inout_ SyncLockWithStatusT&& other  
);  
  
explicit SyncLockWithStatusT(  
   typename SyncTraits::Type sync,  
   DWORD status  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *other*  
 Ссылка rvalue на другой **SyncLockWithStatusT** объекта.  
  
 *sync*  
 Ссылка на другой **SyncLockWithStatusT** объекта.  
  
 *status*  
 Значение [status_](../windows/synclockwithstatust-status-data-member.md) данными-членом *других* параметр или *синхронизации* параметра.  
  
## <a name="remarks"></a>Примечания  
 Инициализирует новый экземпляр класса **SyncLockWithStatusT** класса.  
  
 Первый конструктор инициализирует текущий **SyncLockWithStatusT** из другого объекта **SyncLockWithStatusT** заданный параметром *других*, а затем Делает недействительной другой **SyncLockWithStatusT** объекта. Второй конструктор является **защищенные**и инициализирует текущий **SyncLockWithStatusT** объекта в недопустимом состоянии.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)   
 [Метод SyncLockWithStatusT::GetStatus](../windows/synclockwithstatust-getstatus-method.md)