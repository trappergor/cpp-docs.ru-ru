---
title: "Деструктор SyncLockT::~SyncLockT | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~SyncLockT, деструктор"
ms.assetid: 9e14870d-017d-45fe-a3dc-cd86b6fa1c3a
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Деструктор SyncLockT::~SyncLockT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
~SyncLockT();  
```  
  
## Примечания  
 Деинициализирует экземпляр класса SyncLockT.  
  
 Этот деструктор также разблокирует текущий экземпляр SyncLockT.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## См. также  
 [Класс SyncLockT](../windows/synclockt-class.md)