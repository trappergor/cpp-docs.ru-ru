---
title: "Метод Semaphore::Lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock - метод"
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Метод Semaphore::Lock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ожидает, пока текущий объект или объект семафора, связанный с указанным дескриптором, не будет находиться в сигнальном состоянии или указанный интервал времени ожидания истечет.  
  
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
 Дескриптор объекта семафора.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Details::SyncLockWithStatusT\<HandleTraits::SemaphoreTraits>  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
[Класс Semaphore](../windows/semaphore-class.md)
 