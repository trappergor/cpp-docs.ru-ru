---
title: "Метод SRWLock::TryLockShared | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLockShared - метод"
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод SRWLock::TryLockShared
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Пытается получить объект SRWLock в режиме общего доступа для текущего или указанного объекта SRWLock.  
  
## Синтаксис  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### Параметры  
 `lock`  
 Указатель на объект SRWLock.  
  
## Возвращаемое значение  
 В случае успеха — объект SRWLock в режиме общего доступа и вызывающий поток получает право на владение блокировкой.  В противном случае — объект SRWLock, состояние которого является недопустимым.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс SRWLock](../windows/srwlock-class.md)