---
title: "Метод SRWLock::TryLockExclusive | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLockExclusive - метод"
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод SRWLock::TryLockExclusive
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Пытается получить объект SRWLock в монопольном режиме для текущего или указанного объекта SRWLock.  Если вызов завершился успешно, то вызывающий поток получает владение блокировкой.  
  
## Синтаксис  
  
```  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### Параметры  
 `lock`  
 Указатель на объект SRWLock.  
  
## Возвращаемое значение  
 В случае успеха — объект SRWLock в режиме монопольного доступа и вызывающий поток получает право на владение блокировкой.  В противном случае — объект SRWLock, состояние которого является недопустимым.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс SRWLock](../windows/srwlock-class.md)