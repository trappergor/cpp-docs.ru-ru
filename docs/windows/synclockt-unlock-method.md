---
title: "Метод SyncLockT::Unlock | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock - метод"
ms.assetid: e21110a2-03dd-4073-9c3f-73b99e39f405
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод SyncLockT::Unlock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
void Unlock();  
```  
  
## Заметки  
 Освобождает управление ресурсом, удерживаемого текущим объектом SyncLockT, если таковые имеются.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## См. также  
 [Класс SyncLockT](../windows/synclockt-class.md)