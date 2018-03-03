---
title: "Конструктор SyncLockWithStatusT::SyncLockWithStatusT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT, constructor
ms.assetid: 5d2fb820-ae1b-495f-8084-ebb4fecc3104
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc5be4a37182cb23b47a2511d2e7d5eb0ffa558a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
#### <a name="parameters"></a>Параметры  
 `other`  
 Ссылка rvalue на другом объекте SyncLockWithStatusT.  
  
 `sync`  
 Ссылка на другом объекте SyncLockWithStatusT.  
  
 `status`  
 Значение [status_](../windows/synclockwithstatust-status-data-member.md) данными-членом `other` параметр или `sync` параметра.  
  
## <a name="remarks"></a>Примечания  
 Инициализирует новый экземпляр класса SyncLockWithStatusT.  
  
 Первый конструктор инициализирует текущий объект SyncLockWithStatusT из другой SyncLockWithStatusT, заданного параметром `other`, а затем становятся недействительными объекте SyncLockWithStatusT. Второй конструктор не `protected`и инициализирует текущий объект SyncLockWithStatusT в недопустимом состоянии.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [SyncLockWithStatusT-класс](../windows/synclockwithstatust-class.md)   
 [Метод SyncLockWithStatusT::GetStatus](../windows/synclockwithstatust-getstatus-method.md)