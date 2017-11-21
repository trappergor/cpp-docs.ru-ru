---
title: "Метод SyncLockWithStatusT::IsLocked | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs: C++
helpviewer_keywords: IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e31f0931a53e8bdd977e82fcef56f1bacc45f76b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="synclockwithstatustislocked-method"></a>Метод SyncLockWithStatusT::IsLocked
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
bool IsLocked() const;  
```  
  
## <a name="remarks"></a>Примечания  
 Указывает, владеет ли текущий объект SyncLockWithStatusT ресурса; SyncLockWithStatusT объект является *заблокирован*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если объекте SyncLockWithStatusT заблокирован; в противном случае — **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)