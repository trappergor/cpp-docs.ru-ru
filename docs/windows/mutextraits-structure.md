---
title: "Структура MutexTraits | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MutexTraits - структура"
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура MutexTraits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет общие характеристики класса [Mutex](../Topic/Mutex%20Class1.md).  
  
## Синтаксис  
  
```  
struct MutexTraits : HANDLENullTraits;  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод MutexTraits::Unlock](../windows/mutextraits-unlock-method.md)|Выпускает эксклюзивный элемент управления общими ресурсами.|  
  
## Иерархия наследования  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)