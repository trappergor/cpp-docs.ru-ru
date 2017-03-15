---
title: "Метод SyncLockWithStatusT::GetStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetStatus - метод"
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Метод SyncLockWithStatusT::GetStatus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат операции ожидания объекта, например основан на класс SyncLockWithStatusT [мьютекс](Mutex%20Class1.md) или [семафора](../windows/semaphore-class.md). Ноль (0) указывает, что операция ожидания возвращается сигнальным; в противном случае — другое состояние произошла, такие как истечения времени ожидания.  
  
## <a name="remarks"></a>Примечания  
 Получает состояние ожидания объекта SyncLockWithStatusT.  
  
 Функция GetStatus() возвращает значение базового [status_](../windows/synclockwithstatust-status-data-member.md) данные-член. Когда объект на основе класса SyncLockWithStatusT выполняет операцию блокировки, объект сначала ожидает объект станет доступным. Результат этой операции ожидания сохраняется в `status_` элемент данных. Возможные значения `status_` член данных – возвращаемого значения операции ожидания. Дополнительные сведения см. в разделе возвращаемые значения **WaitForSingleObjectEx()** функции в библиотеке MSDN.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)