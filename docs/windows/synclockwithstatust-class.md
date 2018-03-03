---
title: "Класс SyncLockWithStatusT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT class
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b4b007acd6e6b9272a4fc7bb256d302cafeb75c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="synclockwithstatust-class"></a>Класс SyncLockWithStatusT
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `SyncTraits`  
 Тип, который может принимать монопольного или общие права владения ресурсом.  
  
## <a name="remarks"></a>Примечания  
 Представляет тип, который может принимать монопольного или общие права владения ресурсом.  
  
 Класс SyncLockWithStatusT используется для реализации [мьютекс](../windows/mutex-class1.md) и [семафора](../windows/semaphore-class.md) классы.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор SyncLockWithStatusT::SyncLockWithStatusT](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Инициализирует новый экземпляр класса SyncLockWithStatusT.|  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор SyncLockWithStatusT::SyncLockWithStatusT](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Инициализирует новый экземпляр класса SyncLockWithStatusT.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод SyncLockWithStatusT::GetStatus](../windows/synclockwithstatust-getstatus-method.md)|Извлекает состояние ожидания в текущем объекте SyncLockWithStatusT.|  
|[Метод SyncLockWithStatusT::IsLocked](../windows/synclockwithstatust-islocked-method.md)|Указывает, владеет ли текущий объект SyncLockWithStatusT ресурса; SyncLockWithStatusT объект является *заблокирован*.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[Элемент данных SyncLockWithStatusT::status_](../windows/synclockwithstatust-status-data-member.md)|Содержит результат базовой операции ожидания после операции блокирования объекта, основанного на текущем объекте SyncLockWithStatusT.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)