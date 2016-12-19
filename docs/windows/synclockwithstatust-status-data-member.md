---
title: "Элемент данных SyncLockWithStatusT::status_ | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "status_ - элемент данных"
ms.assetid: 466fa336-b5ff-4d43-8efd-1e87e5fddf88
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Элемент данных SyncLockWithStatusT::status_
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
DWORD status_;  
```  
  
## Заметки  
 Содержит результат основной операции ожидания после операции блокирования объекта, основанного на текущем объекте SyncLockWithStatusT.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## См. также  
 [Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)