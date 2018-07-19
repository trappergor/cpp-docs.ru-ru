---
title: Конструктор SyncLockWithStatusT::SyncLockWithStatusT | Документы Microsoft
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
ms.openlocfilehash: 8f665866a43e45d6526aa33f17c05eacebdd84aa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891354"
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