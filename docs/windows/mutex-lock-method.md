---
title: "Метод Mutex::LOCK | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 61d95072-b690-441e-a080-0bf94a733141
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e915dee2dbc7f3cc483df2e8135398a12d0fc369
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mutexlock-method"></a>Метод Mutex::Lock
Ожидает, пока текущий объект или объект мьютекса, связанный с указанным дескриптором освобождает объект взаимного исключения или истечения отведенного времени ожидания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `milliseconds`  
 Интервал времени ожидания в миллисекундах. Значение по умолчанию равно INFINITE, что означает неограниченное время ожидания.  
  
 `h`  
 Дескриптор объекта Mutex.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers
 
 ## <a name="see-also"></a>См. также
 [Класс Mutex](../windows/mutex-class1.md)