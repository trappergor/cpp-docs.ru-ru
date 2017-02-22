---
title: "Метод EventTargetArray::AddTail | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::EventTargetArray::AddTail"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddTail - метод"
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Метод EventTargetArray::AddTail
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
void AddTail(  
   _In_ IUnknown* element  
);  
```  
  
#### Параметры  
 `element`  
 Указатель на обработчик событий, который необходимо добавить.  
  
## Примечания  
 Добавляет указанный обработчик событий в конец внутреннего массива обработчиков событий.  
  
 AddTail\(\) предназначено для внутреннего использования в классе EventSource.  
  
## Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Класс EventTargetArray](../windows/eventtargetarray-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)