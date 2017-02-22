---
title: "Метод SRWLock::LockExclusive | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LockExclusive - метод"
ms.assetid: f361b672-fca6-45cc-a9b4-310cc0d23fdc
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод SRWLock::LockExclusive
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает объект SRWLock в монопольном режиме.  
  
## Синтаксис  
  
```  
SyncLockExclusive LockExclusive();  
  
static SyncLockExclusive LockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### Параметры  
 `lock`  
 Указатель на объект SRWLock.  
  
## Возвращаемое значение  
 Объект SRWLock в монопольном режиме.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс SRWLock](../windows/srwlock-class.md)