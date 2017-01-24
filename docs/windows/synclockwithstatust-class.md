---
title: "Класс SyncLockWithStatusT | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockWithStatusT - класс"
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс SyncLockWithStatusT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `SyncTraits`  
 Тип, который может принимать монопольного или общего владельца ресурса.  
  
## <a name="remarks"></a>Примечания  
 Представляет тип, который может принимать монопольного или общего владельца ресурса.  
  
 Класс SyncLockWithStatusT используется для реализации [мьютекс](../Topic/Mutex%20Class1.md) и [семафора](../windows/semaphore-class.md) классы.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор SyncLockWithStatusT::SyncLockWithStatusT](../Topic/SyncLockWithStatusT::SyncLockWithStatusT%20Constructor.md)|Инициализирует новый экземпляр класса SyncLockWithStatusT.|  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор SyncLockWithStatusT::SyncLockWithStatusT](../Topic/SyncLockWithStatusT::SyncLockWithStatusT%20Constructor.md)|Инициализирует новый экземпляр класса SyncLockWithStatusT.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод SyncLockWithStatusT::GetStatus](../windows/synclockwithstatust-getstatus-method.md)|Получает состояние ожидания объекта SyncLockWithStatusT.|  
|[Метод SyncLockWithStatusT::IsLocked](../windows/synclockwithstatust-islocked-method.md)|Указывает, владеет ли текущий объект SyncLockWithStatusT ресурса; Объект SyncLockWithStatusT является *заблокирован*.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Элемент данных Synclockwithstatust::status_](../windows/synclockwithstatust-status-data-member.md)|Содержит результат базовой операции ожидания после операции блокирования объекта, основанного на текущем объекте SyncLockWithStatusT.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также раздел  
 [Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)