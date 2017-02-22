---
title: "Элемент данных InvokeHelper::callback_ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::InvokeHelper::callback_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "callback_ - элемент данных"
ms.assetid: 6f0cbf6d-0448-46f8-ba71-bd6fd8702e3a
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Элемент данных InvokeHelper::callback_
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
TCallback callback_;  
```  
  
## Примечания  
 Представляет обработчик события для вызова, когда происходит событие.  
  
 Параметр шаблона `TCallback` задает тип обработчика событий.  
  
## Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Структура InvokeHelper](../windows/invokehelper-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)