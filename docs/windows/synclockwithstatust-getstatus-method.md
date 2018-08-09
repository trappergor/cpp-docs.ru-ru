---
title: Метод SyncLockWithStatusT::GetStatus | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a54cab831d3e3180a28f892fcf37c7351c22bc33
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014966"
---
# <a name="synclockwithstatustgetstatus-method"></a>Метод SyncLockWithStatusT::GetStatus
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Результат операции ожидания на объект, который основан на **SyncLockWithStatusT** класс, например [мьютекс](../windows/mutex-class1.md) или [семафора](../windows/semaphore-class.md). Ноль (0) указывает, что операция ожидания возвращается в сигнальном состоянии; в противном случае — другой возникло состояние, такие как прошедшее значение времени ожидания.  
  
## <a name="remarks"></a>Примечания  
 Получает сведения о состоянии ожидания текущего **SyncLockWithStatusT** объекта.  
  
 Функция GetStatus() извлекает значение базового [status_](../windows/synclockwithstatust-status-data-member.md) данные-член. Если создан на основе объекта **SyncLockWithStatusT** класс выполняет операцию блокировки, объект сначала ожидает объект станет доступным. Результат этой операции ожидания сохраняется в `status_` элемент данных. Возможные значения `status_` элемент данных являются возвращаемыми значениями для операции ожидания. Дополнительные сведения см. в разделе возвращаемые значения `WaitForSingleObjectEx()` функция в библиотеке MSDN.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)