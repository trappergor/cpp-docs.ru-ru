---
title: "Метод SemaphoreTraits::Unlock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock - метод"
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод SemaphoreTraits::Unlock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выпускает элемент управления общими ресурсами.  
  
## Синтаксис  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### Параметры  
 `h`  
 Дескриптор объекта семафора.  
  
## Примечания  
 Если операция разблокирования завершилась неудачей, то Unlock\(\) выдает ошибку, которая указывает на причину сбоя.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Структура SemaphoreTraits](../Topic/SemaphoreTraits%20Structure.md)