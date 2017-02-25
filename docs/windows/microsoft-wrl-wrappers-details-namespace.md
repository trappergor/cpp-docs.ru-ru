---
title: "Пространство имен Microsoft::WRL::Wrappers::Details | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details"
  - "internal/Microsoft::WRL::Details"
  - "async/Microsoft::WRL::Details"
  - "corewrappers/Microsoft::WRL::Wrappers::Details"
  - "client/Microsoft::WRL::Details"
  - "module/Microsoft::WRL::Details"
  - "event/Microsoft::WRL::Details"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Details - пространство имен"
ms.assetid: 6d3f04ac-9b53-4a82-a188-a85309ec34a4
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Пространство имен Microsoft::WRL::Wrappers::Details
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
namespace Microsoft::WRL::Wrappers::Details;  
```  
  
## Члены  
  
### Классы  
  
|Имя|Описание|  
|---------|--------------|  
|[Класс SyncLockT](../windows/synclockt-class.md)|Представляет собой тип, который может получать ресурс в монопольное или совместное владение.|  
|[Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)|Представляет собой тип, который может получать ресурс в монопольное или совместное владение.|  
  
### Методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод CompareStringOrdinal](../windows/comparestringordinal-method.md)|Сравнивает два указанных объекта `HSTRING` и возвращает целое число, которое показывает их относительное положение в порядке сортировки.|  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)