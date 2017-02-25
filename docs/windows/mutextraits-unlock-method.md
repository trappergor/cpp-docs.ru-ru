---
title: "Метод MutexTraits::Unlock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock - метод"
ms.assetid: 7c4e5664-6d95-498a-95bb-d30b5e866c2c
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод MutexTraits::Unlock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выпускает эксклюзивный элемент управления общими ресурсами.  
  
## Синтаксис  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### Параметры  
 `h`  
 Дескриптор объекта мьютекса.  
  
## Возвращаемое значение  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Структура MutexTraits](../windows/mutextraits-structure.md)