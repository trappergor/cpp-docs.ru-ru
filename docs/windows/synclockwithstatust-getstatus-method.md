---
title: "Метод SyncLockWithStatusT::GetStatus | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs: C++
helpviewer_keywords: GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 181735766e62aa1bf8c306bd425c6e6b03b2066d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="synclockwithstatustgetstatus-method"></a>Метод SyncLockWithStatusT::GetStatus
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат операции ожидания на объект, который основан на класс SyncLockWithStatusT, такие как [мьютекс](../windows/mutex-class1.md) или [семафора](../windows/semaphore-class.md). Ноль (0) указывает, что операция ожидания возвращается сигнальное состояние; в противном случае другое состояние произошла, такие как истекло время ожидания.  
  
## <a name="remarks"></a>Примечания  
 Извлекает состояние ожидания в текущем объекте SyncLockWithStatusT.  
  
 Функция GetStatus() возвращает значение базового [status_](../windows/synclockwithstatust-status-data-member.md) члена данных. Если объект по SyncLockWithStatusT-класс выполняет операцию блокировки, объект сначала ожидает объект станет доступен. Результат этой операции ожидания сохраняется в `status_` элемент данных. Возможные значения `status_` член данных являются возвращаемыми значениями операции ожидания. Дополнительные сведения см. в разделе возвращаемых значений **WaitForSingleObjectEx()** функции в библиотеке MSDN.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)