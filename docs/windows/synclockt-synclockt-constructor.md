---
title: Конструктор SyncLockT::SyncLockT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c3353df1a73821a2009aeba2367f1892b06aba5b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889849"
---
# <a name="synclocktsynclockt-constructor"></a>Конструктор SyncLockT::SyncLockT
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `other`  
 Ссылка rvalue на другой объект SyncLockT.  
  
 `sync`  
 Ссылка на другом объекте SyncLockWithStatusT.  
  
## <a name="remarks"></a>Примечания  
 Инициализирует новый экземпляр класса SyncLockT.  
  
 Первый конструктор инициализирует текущий объект SyncLockT из другого объекта SyncLockT, заданного параметром `other`, а затем становятся недействительными и другой объект SyncLockT. Второй конструктор не `protected`и инициализирует текущий объект SyncLockT в недопустимом состоянии.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Класс SyncLockT](../windows/synclockt-class.md)