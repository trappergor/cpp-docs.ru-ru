---
title: "Метод SyncLockWithStatusT::IsLocked | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsLocked - метод"
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод SyncLockWithStatusT::IsLocked
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
bool IsLocked() const;  
```  
  
## Заметки  
 Указывает, владеет ли текущий объект SyncLockWithStatusT ресурсом; иными словами, объект SyncLockWithStatusT *блокирован*.  
  
## Возвращаемое значение  
 **true**, если объект SyncLockWithStatusT заблокирован; в противном случае — значение **false**.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## См. также  
 [Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)