---
title: "Класс out_of_memory | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::out_of_memory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out_of_memory - класс"
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Класс out_of_memory
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Исключение, возникающее, если выполнение метода завершается ошибкой из\-за отсутствия памяти системы или устройства.  
  
## Синтаксис  
  
```  
class out_of_memory : public runtime_exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор out\_of\_memory::out\_of\_memory](../Topic/out_of_memory::out_of_memory%20Constructor.md)|Инициализирует новый экземпляр класса `out_of_memory`.|  
  
## Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)