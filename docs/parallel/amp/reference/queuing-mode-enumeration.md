---
title: "Перечисление queuing_mode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::queuing_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queuing_mode - перечисление"
ms.assetid: 8c641054-906d-40b3-bbb4-f62af9356a14
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Перечисление queuing_mode
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Определяет режимы организации очереди, поддерживаемые ускорителем.  
  
## Синтаксис  
  
```  
enum queuing_mode;  
```  
  
## Члены  
  
### Значения  
  
|Name|Описание|  
|----------|--------------|  
|`queuing_mode_immediate`|Режим организации очереди, указывающий, что любые команды, например [Функция parallel\_for\_each \(C\+\+ AMP\)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md), отправляются в соответствующий ускоритель, как только они возвращаются вызывающему объекту.|  
|`queuing_mode_automatic`|Режим организации очереди, указывающий, что команды будут ставиться в очередь, которая соответствует объекту [accelerator\_view](../Topic/accelerator_view%20Class.md).  Команды отправляются на устройство при вызове [accelerator\_view::flush](../Topic/accelerator_view::flush%20Method.md).|  
  
## Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)