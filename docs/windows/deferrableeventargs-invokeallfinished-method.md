---
title: "Метод DeferrableEventArgs::InvokeAllFinished | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод DeferrableEventArgs::InvokeAllFinished
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызывается, чтобы указать, что вся обработка для отложенного события завершена.  
  
## Синтаксис  
  
```cpp  
void InvokeAllFinished()  
```  
  
## Заметки  
 Этот метод следует вызывать после того, как источник события вызовет [InvokeAll](../windows/eventsource-invokeall-method.md).  Вызов этого метода предотвращает ввод последующих задержек и вызывает принудительное выполнение обработчика завершения, если задержки отсутствовали.  
  
 Пример кода см. в разделе [Класс DeferrableEventArgs](../windows/deferrableeventargs-class.md).  
  
## Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс DeferrableEventArgs](../windows/deferrableeventargs-class.md)   
 [Метод EventSource::InvokeAll](../windows/eventsource-invokeall-method.md)